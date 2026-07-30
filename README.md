# Postmoni — Public API docs (Mintlify)

Mintlify documentation for the Postmoni Public API. The API reference is generated from the
OpenAPI spec at [`api-reference/openapi.yaml`](api-reference/openapi.yaml).

## Run locally

```bash
npm i -g mint            # one-time (CLI)
cd postmoni-docs
mint dev                 # http://localhost:3000
```

> Or without installing globally: `npx mint dev`

## Structure

```
docs.json                    Site config (theme, navigation, branding)
index.mdx                    Overview
quickstart.mdx               First money order
authentication.mdx          API keys, headers, key security
errors.mdx                   Status codes & error envelope
concepts/                    Onboarding, corridors, money order lifecycle
guides/                      Full integration flow, sandbox testing
api-reference/openapi.yaml   OpenAPI 3.1 spec → auto-generated endpoint pages
```

## Keep the spec in sync

`api-reference/openapi.yaml` is the source of truth for the reference pages. When you change the
Public API (`src/core/public/public-api/`), update the spec to match — the endpoints, request
bodies, and response shapes here mirror `public-money-order.controller.ts`, its DTOs, and
`public-money-order.types.ts`.

## Deploy

Connect this repo to Mintlify (mintlify.com) and set the **docs directory** to `postmoni-docs`.
Pushes to the default branch auto-publish.
