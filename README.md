# postgres-prisma-nextjs-tailwind-users

# 🚀 Seeds database with 3 users including Avatars. Simple Next.js template that uses Vercel Postgres as the database and Prisma as the ORM. 🚀

```java
model users {
  id        Int      @id @default(autoincrement())
  name      String
  email     String   @unique
  image     String
  createdAt DateTime @default(now())
}
```

https://github.com/coding-to-music/postgres-prisma-nextjs-tailwind-users

https://postgres-prisma-nextjs-tailwind-users.vercel.app

From / By https://vercel.com/templates/next.js/postgres-prisma

https://postgres-prisma.vercel.app/

<!-- <div style="text-align:center;">
  <img src="/images/chakra.jpg" alt="Image" />
  <p><em>Chakra Component Library with Next.js</em></p>
</div> -->

## Node Environment:

```java
nvm use 18
```

## Environment variables:

see `.env-example`

```java
POSTGRES_PRISMA_URL=
POSTGRES_URL_NON_POOLING=

# This is used by prisma:
#   url       = env("POSTGRES_PRISMA_URL") // uses connection pooling
#   directUrl = env("POSTGRES_URL_NON_POOLING") // uses a direct connection
```

## GitHub

```java
git init
git add .
git remote remove origin
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:coding-to-music/postgres-prisma-nextjs-tailwind-users.git
git push -u origin main
```

- name: Vercel Postgres + Prisma Next.js Starter
- slug: postgres-prisma
- description: Simple Next.js template that uses Vercel Postgres as the database and Prisma as the ORM.
- framework: Next.js
- useCase: Starter
- css: Tailwind
- database: Vercel Postgres
- demoUrl: https://postgres-prisma.vercel.app/

# Vercel Postgres + Prisma Next.js Starter

Simple Next.js template that uses [Vercel Postgres](https://vercel.com/postgres) as the database and [Prisma](https://prisma.io/) as the ORM.

## Demo

https://postgres-prisma.vercel.app/

## How to Use

You can choose from one of the following two methods to use this repository:

### One-Click Deploy

Deploy the example using [Vercel](https://vercel.com?utm_source=github&utm_medium=readme&utm_campaign=vercel-examples):

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fvercel%2Fexamples%2Ftree%2Fmain%2Fstorage%2Fpostgres-prisma&project-name=postgres-prisma&repository-name=postgres-prisma&demo-title=Vercel%20Postgres%20%2B%20Prisma%20Next.js%20Starter&demo-description=Simple%20Next.js%20template%20that%20uses%20Vercel%20Postgres%20as%20the%20database%20and%20Prisma%20as%20the%20ORM.&demo-url=https%3A%2F%2Fpostgres-prisma.vercel.app%2F&demo-image=https%3A%2F%2Fpostgres-prisma.vercel.app%2Fopengraph-image.png&stores=%5B%7B"type"%3A"postgres"%7D%5D)

### Clone and Deploy

Execute [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app) with [pnpm](https://pnpm.io/installation) to bootstrap the example:

```bash
pnpm create next-app --example https://github.com/vercel/examples/tree/main/storage/postgres-prisma
```

Once that's done, copy the .env.example file in this directory to .env.local (which will be ignored by Git):

```bash
cp .env.example .env.local
```

Then open `.env.local` and set the environment variables to match the ones in your Vercel Storage Dashboard.

Next, run Next.js in development mode:

```bash
pnpm dev
```

Deploy it to the cloud with [Vercel](https://vercel.com/new?utm_source=github&utm_medium=readme&utm_campaign=vercel-examples) ([Documentation](https://nextjs.org/docs/deployment)).

# Setup Prisma database

```java
npx prisma db push
```

## View prisma studio

```java
npx prisma studio
```

## Run in Dev

```java
yarn dev
```

## Build and Seed the database

```java
yarn build
```

Output

```java
yarn run v1.22.19
$ prisma generate && prisma db push && prisma db seed && next build
Environment variables loaded from .env
Prisma schema loaded from prisma/schema.prisma

✔ Generated Prisma Client (5.1.1 | library) to ./node_modules/@prisma/client in 108ms
You can now start using Prisma Client in your code. Reference: https://pris.ly/d/client
```

import { PrismaClient } from '@prisma/client'
const prisma = new PrismaClient()

```
Environment variables loaded from .env
Prisma schema loaded from prisma/schema.prisma
Datasource "db": PostgreSQL database "neondb", schema "public" at "ep-floral-glitter-26719508.us-east-1.aws.neon.tech"

The database is already in sync with the Prisma schema.

✔ Generated Prisma Client (5.1.1 | library) to ./node_modules/@prisma/client in 245ms

Environment variables loaded from .env
Running seed command `ts-node --compiler-options {"module":"CommonJS"} prisma/seed.ts` ...
[
  {
    id: 3,
    name: 'Guillermo Rauch',
    email: 'rauchg@vercel.com',
    image: 'https://pbs.twimg.com/profile_images/1576257734810312704/ucxb4lHy_400x400.jpg',
    createdAt: 2023-08-19T02:42:12.588Z
  },
  {
    id: 2,
    name: 'Lee Robinson',
    email: 'lee@vercel.com',
    image: 'https://pbs.twimg.com/profile_images/1587647097670467584/adWRdqQ6_400x400.jpg',
    createdAt: 2023-08-19T02:42:12.588Z
  },
  {
    id: 1,
    name: 'Steven Tey',
    email: 'stey@vercel.com',
    image: 'https://pbs.twimg.com/profile_images/1506792347840888834/dS-r50Je_400x400.jpg',
    createdAt: 2023-08-19T02:42:12.339Z
  }
]

🌱  The seed command has been executed.
- info Loaded env from /home/tmc/ap/vol7/postgres-prisma-nextjs-tailwind-users/.env
- info Creating an optimized production build
- info Compiled successfully
- info Linting and checking validity of types
- info Collecting page data
- info Generating static pages (4/4)
- info Finalizing page optimization

Route (app)                                Size     First Load JS
┌ λ /                                      11 kB          89.3 kB
├ ○ /favicon.ico                           0 B                0 B
└ ○ /opengraph-image.png                   0 B                0 B
+ First Load JS shared by all              78.3 kB
  ├ chunks/596-e8c2339c01193ad7.js         25.9 kB
  ├ chunks/fd9d1056-30d3a909b5b695ab.js    50.5 kB
  ├ chunks/main-app-55ac41cb23d20399.js    215 B
  └ chunks/webpack-66b298d41f99209c.js     1.67 kB

Route (pages)                              Size     First Load JS
─ ○ /404                                   182 B          75.7 kB
+ First Load JS shared by all              75.5 kB
  ├ chunks/framework-8883d1e9be70c3da.js   45 kB
  ├ chunks/main-2f9cd91d74910ef6.js        28.6 kB
  ├ chunks/pages/_app-52924524f99094ab.js  195 B
  └ chunks/webpack-66b298d41f99209c.js     1.67 kB

λ  (Server)  server-side renders at runtime (uses getInitialProps or getServerSideProps)
○  (Static)  automatically rendered as static HTML (uses no initial props)

Done in 48.90s.
```
