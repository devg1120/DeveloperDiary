
# conmode
Display Windows console modes for stdin, stdout, stderr.  
Or decrypt a console mode integer.

    go install `github.com/VonC/conmode@latest`

## Description

### Display console mode

`conmode.exe` or `conmode.exe display` (the default command), will print:

- `windows.GetConsoleMode` with:
  - `windows.STD_INPUT_HANDLE`
  - `windows.STD_OUTPUT_HANDLE`
  - `windows.STD_ERROR_HANDLE`
- Input/output modes listed from https://docs.microsoft.com/en-us/windows/console/setconsolemode

[<img src="windows_console.png">](https://docs.microsoft.com/en-us/windows/console/setconsolemode)

### Decrypt console mode integer

```bash
console.exe 503
conmode 503: 'ENABLE_ECHO_INPUT|ENABLE_INSERT_MODE|ENABLE_LINE_INPUT|ENABLE_MOUSE_INPUT|ENABLE_PROCESSED_INPUT|ENABLE_QUICK_EDIT_MODE'
```

## License: MIT


---
title: 'Project documentation template'
disqus: hackmd
---

開発日誌　Project Title
===

# Table of Contents

[TOC]


# 方式

### aniways

https://github.com/devg1120/aniways

- #### FrontEnd WEB
     -- Sveltekit /nodejs    SSR
     > lucide-svelte
     > bits-ui
- #### Backend API
     -- java 17+
     -- kotlin ktor
     ```
     DI                 :koin
     ORM                :ktorm
     DB-CONNECTION-POOL :hikari
     DB-MIGRATION-TOOL  :flyway
     DB-DRIVER          :driver.postgres
     DB-DRIVER          :kreds
     ```
     -- Bun
     -- high-performance HLS proxy 
     
---
### sveltekit-hono

https://github.com/devg1120/hono-sveltekit/tree/main/sveltekit-hono


https://github.com/devg1120/hono-sveltekit/tree/main/sveltekit-hono-playground

![hono_playgrand](https://hackmd.io/_uploads/HkWQEQ6mxx.png)

[<img src="windows_console.png">](https://docs.microsoft.com/en-us/windows/console/setconsolemode)


> Using Hono with SvelteKit - Full type-safety with RPC
> 
(https://dev.to/bop/using-hono-with-sveltekit-full-type-safety-with-rpc-2h7)

lib/api.ts
``` ts
export const Task = z.object({
	id: z.string().uuid(),
	name: z.string().min(1),
	done: z.boolean()
});

export type Task = z.infer<typeof Task>;

export const TaskCreateInput = Task.pick({ name: true });

export type TaskCreateInput = z.infer<typeof TaskCreateInput>;

export const TaskParam = Task.pick({ id: true });
export type TaskParam = z.infer<typeof TaskParam>;

/**
 * This will be our in-memory data store
 */
let tasks: Task[] = [];

export const router = new Hono()
	.get('/tasks', (c) => c.json<Task[]>(tasks))
	.post('/tasks', zValidator('json', TaskCreateInput), (c) => {
		const body = c.req.valid('json');
		const task = {
			id: crypto.randomUUID(),
			name: body.name,
			done: false
		};
		tasks = [...tasks, task];
		return c.json(task);
	})
	.post('/tasks/:id/finish', zValidator('param', TaskParam), (c) => {
		const { id } = c.req.valid('param');
		const task = tasks.find((task) => task.id === id);
		if (task) {
			task.done = true;
			return c.json(task);
		}

		throw c.json({ message: 'Task not found' }, 404);
	})

```




Schema and Types

- [drizzle-orm]()
- [drizzle-zod]()
- [zod]()
- [@hono/zod-validator]()

Database and tools

- [postgres]()
- [drizzle-kit]()
- [tsx]()

Authentication

- [lucia]()
- [oslo]()

Utils

- [pino]()
- [pino-pretty]()
- [decode-formdata]()
- [date-fns]()

---
### hono-kysely-db

https://github.com/devg1120/kysely-test

- sqlite
- postgres
- cockroachdb

---

### sveltekit tec

- tRPC
https://github.com/devg1120/sveltekit-tec/tree/main/sveltekit-tRPC-app
  
- SSE 
https://github.com/devg1120/sveltekit-tec/tree/main/sveltekit-SSE-app

- Hyd
https://github.com/devg1120/sveltekit-tec/tree/main/sveltekit-Store-Hyd-app

---

### Kotlin/Ktor認証

https://github.com/devg1120/ktor-auth-example

| kotin  ktor

- auth-from-session
- auth-jwt-rs256


---
### Svelte Postgresql app

1. node-pg ONLY   not ORM

>  https://github.com/devg1120/sveltekit-psql-app
>   - postgres
>   - 生SQLコード
>   - insert delete


2. ORM prisma 

 >https://github.com/devg1120/sveltekit-db-app
  > - ToDo app
  > - sqlite
  > - prisma
  > - socket.io
 
