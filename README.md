# create-bunigniter

[![npm](https://img.shields.io/npm/v/create-bunigniter)](https://www.npmjs.com/package/create-bunigniter)
[![CI](https://github.com/kabyeon/create-bunigniter/actions/workflows/ci.yml/badge.svg)](https://github.com/kabyeon/create-bunigniter/actions)

**BunIgniter project scaffolding tool**

Start a [BunIgniter](https://github.com/kabyeon/bunigniter) full-stack MVC project — a CodeIgniter 3-style Bun framework — with a single command.

## Usage

```bash
bunx create-bunigniter@latest my-app
```

```bash
bunx create-bunigniter@latest blog
```

Running the command will:

1. Create the project directory
2. Install the `bunigniter` package
3. Scaffold the project with `bunigniter init`

## Prerequisites

- [Bun](https://bun.sh) >= 1.0.0

## Getting Started

```bash
cd my-app
bun run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## CLI Commands

Available commands after project creation:

```bash
bun run bi make:scaffold post --fields=title:string,content:text  # Full CRUD
bun run bi make:scaffold post --api --fields=title:string         # API only
bun run bi migrate                                               # Run migrations
bun run bi migrate:rollback                                      # Rollback migrations
bun run bi db:seed                                               # Run seeders
bun run bi list:routes                                           # List routes
```

## Links

| Link | Description |
|------|-------------|
| [BunIgniter](https://github.com/kabyeon/bunigniter) | Framework repository |
| [Docs](https://github.com/kabyeon/bunigniter/tree/main/docs/user-guide) | Feature documentation |
| [Bun](https://bun.sh) | Bun runtime |

## License

MIT
