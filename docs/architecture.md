# Local Pulse - Google Maps CTR Automation Platform - architecture

Two cooperating processes in one repository: a Next.js dashboard as the command centre, and a Node/Express + Playwright backend that drives a fleet of isolated browser profiles on a Linux VPS. The dashboard talks to the live backend over a typed API layer; campaigns, workers and results are persisted so every run is reproducible and attributable.

## Components

### Dashboard (Next.js)

Campaign configuration, live run monitoring, multi-tenant views

### Automation backend

Node/Express service driving Playwright browser profiles

### Browser fleet

Isolated profiles with per-profile fingerprint and proxy handling

### Pipelines and workers

Queued jobs for search, referral and reporting flows

### Postgres

Campaign, run and result persistence

## Stack

| Layer | Technology |
| --- | --- |
| Frontend | Next.js, TypeScript |
| Backend | Node.js, Express |
| Automation | Playwright |
| Database | PostgreSQL |
| Infrastructure | Linux VPS, loopback-bound services |

Designed and implemented by Muhammad Tanveer - Full-Stack AI Automation Engineer.