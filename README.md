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
### hono-kysely-edb

https://github.com/devg1120/kysely-test

- sqlite
- postgres
- cockroachdb


---

### Kotlin/Ktor認証

https://github.com/devg1120/ktor-auth-example

| kotin  ktor

- auth-from-session
- auth-jwt-rs256


---
### Svelte Postgresql app

1. node-pg ONLY   not ORM

  https://github.com/devg1120/sveltekit-psql-app

   - 生SQLコード
   - insert delete


