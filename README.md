# create-bunigniter

[![npm](https://img.shields.io/npm/v/create-bunigniter)](https://www.npmjs.com/package/create-bunigniter)
[![CI](https://github.com/nexus-ts/create-bunigniter/actions/workflows/ci.yml/badge.svg)](https://github.com/nexus-ts/create-bunigniter/actions)

**Scaffold a [Bunigniter](https://github.com/nexus-ts/bunigniter) project in seconds.**

Bunigniter is a Bun-native fullstack framework — CodeIgniter's DX × Elysia v2 performance × Edge-ready.

```bash
bun create bunigniter my-app
cd my-app
bun run seed
bun run dev
# → http://localhost:3000
```

---

## Why Bunigniter?

PHP developers (CodeIgniter, Laravel) moving to TypeScript hit a wall: NestJS over-engineers everything, Hono is too bare, AdonisJS is Node-only. **Bunigniter is the bridge.**

```ts
// routes/users.ts — file path = URL
export class Users extends Controller {
  async index()  { return this.json(await this.db.get('users')) }
  async show(id) { return this.json(await this.db.first('SELECT * FROM users WHERE id = ?', [id])) }
  async create() {
    const data = this.request.only(['name', 'email'])
    const v = this.validate(data, { name: 'required|min:2', email: 'required|email' })
    if (v.fails()) return this.badRequest(v.errors)
    await this.db.insert('users', { name: v.data.name, email: v.data.email })
    return this.json({ ok: true }, 201)
  }
}
```

---

## Usage

```bash
bun create bunigniter           # Interactive prompt
bun create bunigniter my-app    # With project name
npx create-bunigniter my-app    # npm alternative
```

The CLI scaffolds a working project with CRUD, API handler, database seeder, and styled templates — 17 files ready to run.

---

## What you get

```
my-app/
├── config/app.ts           # DB, port, middleware, CORS
├── routes/
│   ├── index.ts            # GET  / — redirect to /items
│   ├── items.ts            # CRUD controller (class-based)
│   ├── items/new.ts        # GET  /items/new — create form
│   ├── welcome.ts          # GET  /welcome — Rendu template
│   ├── api.ts              # GET|POST /api — handler-style
│   └── schedule.ts         # GET  /schedule — cron demo
├── views/
│   ├── _layout.html        # Auto-layout wrapper
│   ├── welcome.html        # Rendu template (PHP-style)
│   ├── items.html          # Items list + CRUD forms
│   └── new-item.html       # Create form
├── db/seed.ts              # SQLite seeder w/ sample data
├── dev.ts                  # Entry point
├── package.json            # Scripts: dev, seed, bi, repl
└── tsconfig.json           # JSX + Bundler resolution
```

---

## What it demonstrates

| Feature | File | Example |
|---------|------|---------|
| Class-based controller | `routes/items.ts` | `this.db`, `this.validate()`, `this.view()`, `this.redirect()` |
| Handler-style routes | `routes/api.ts` | `defineHandler` + Zod validation |
| Rendu templates | `views/*.html` | `<?= variable ?>`, `<? for(...) { ?>` |
| Auto-layout | `views/_layout.html` | `<?= slot ?>` wraps all pages |
| Scheduled tasks | `routes/schedule.ts` | `schedule.every(10000).do(fn)` |
| SQLite | `db/seed.ts` | Zero-config, auto-created |
| Input validation | Controller | CI-style string rules or Zod schemas |
| Request API | Controller | `this.request.only()`, `.get()`, `.post()`, `.has()`, etc. |

---

## Quick Start

```bash
cd my-app
bun run seed      # Seed database (3 sample items)
bun run dev       # Dev server at :3000
bun run bi repl   # Interactive REPL with db, cache, http
bun run bi list   # List all registered routes
```

---

## Requirements

- [Bun](https://bun.sh) >= 1.3.0

---

## Next Steps

| Feature | Guide |
|---------|-------|
| Database | Switch dialect in `config/app.ts` (postgres, mysql, d1) |
| Auth | Session/JWT — `import { jwt } from "bunigniter/helpers/jwt"` |
| WebSocket | `routes/ws.ts` — `ws.handle("/chat", { message(ws, data) })` |
| SSE | `import { sse } from "bunigniter/helpers/sse"` |
| HMVC | `modules/<name>/routes/` — modular sub-apps |
| OpenAPI | Auto-generated at `/openapi` with Scalar UI |
| CLI | `bun run bi make:controller`, `make:model`, etc. |
| Edge | `bun run bi build:edge` for Cloudflare Workers |

Full documentation: [github.com/nexus-ts/bunigniter](https://github.com/nexus-ts/bunigniter)

---

## License

MIT
