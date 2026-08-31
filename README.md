# Local Pulse - Google Maps CTR Automation Platform

> Campaign control plane for Google Maps local ranking, driving a Playwright browser fleet from a Next.js dashboard.

Built by **[Muhammad Tanveer](https://www.linkedin.com/in/muhammad-tanveer-advenno/)** - Full-Stack AI Automation Engineer.

[![Source](https://img.shields.io/badge/source-private%20repository-lightgrey)](#source-code-and-access) [![Role](https://img.shields.io/badge/built%20by-Muhammad%20Tanveer-blue)](https://github.com/haddindeve)

## Contents

- [The problem](#the-problem)
- [The approach](#the-approach)
- [Architecture](#architecture)
- [Tech stack](#tech-stack)
- [Key capabilities](#key-capabilities)
- [Selected code](#selected-code)
- [Results](#results)
- [FAQ](#faq)
- [Source code and access](#source-code-and-access)
- [About the engineer](#about-the-engineer)
- [Related projects](#related-projects)

## The problem

Local-ranking campaigns meant an operator manually driving dozens of browser profiles, with no shared record of what ran, from which profile, or what happened afterwards. Work was unrepeatable and impossible to audit across clients.

## The approach

Two cooperating processes in one repository: a Next.js dashboard as the command centre, and a Node/Express + Playwright backend that drives a fleet of isolated browser profiles on a Linux VPS. The dashboard talks to the live backend over a typed API layer; campaigns, workers and results are persisted so every run is reproducible and attributable.

## Architecture

| Component | Responsibility |
| --- | --- |
| **Dashboard (Next.js)** | Campaign configuration, live run monitoring, multi-tenant views |
| **Automation backend** | Node/Express service driving Playwright browser profiles |
| **Browser fleet** | Isolated profiles with per-profile fingerprint and proxy handling |
| **Pipelines and workers** | Queued jobs for search, referral and reporting flows |
| **Postgres** | Campaign, run and result persistence |

## Tech stack

| Layer | Technology |
| --- | --- |
| Frontend | Next.js, TypeScript |
| Backend | Node.js, Express |
| Automation | Playwright |
| Database | PostgreSQL |
| Infrastructure | Linux VPS, loopback-bound services |

## Key capabilities

- Campaign control plane for Maps local-ranking work
- Playwright fleet with per-profile isolation
- Search and referral flow engine
- Multi-tenant separation for agency use
- Deployment runbook for reproducible VPS setup

## Selected code

From `apps/dashboard/lib/api.ts` in the private repository:

```typescript
// lib/api.ts — the single transport layer between the dashboard and the backend
// (Node/Express server at NEXT_PUBLIC_API_BASE). Every endpoint the server
// exposes has a typed wrapper here. The data shapes returned match lib/mock.ts
// exactly, so the mock stays a drop-in fallback (see lib/hooks.ts).
//
// This module is isomorphic (uses fetch, works in server + client components).
// The React hooks that add mock-fallback + loading state live in lib/hooks.ts.

import type {
  Profile,
  DriverTraits,
  Client,
  Business,
  Campaign,
  LiveSession,
  AlertItem,
  QueueJob,
  BusinessKeyword,
  KeywordCorpus,
  EnrichmentJob,
```

## Results

- Manual browser driving replaced by queued, auditable campaign runs
- Every run attributable to a campaign, profile and result set
- Backend bound to loopback and fronted by the dashboard, keeping automation off the public internet

## FAQ

### What does the platform automate?

It orchestrates browser-profile fleets that perform search and referral flows for Google Maps local-ranking campaigns, and records the outcome of each run.

### Why Playwright rather than a headless HTTP client?

Maps flows depend on real rendering, interaction and session state. Playwright drives an actual browser profile, which an HTTP client cannot reproduce.

### Is it multi-tenant?

Yes - campaigns and results are scoped per tenant so an agency can run several clients from one installation.

### Can I see the code?

The implementation is private. Access can be arranged on request.

## Source code and access

This repository is the public case study for **Local Pulse - Google Maps CTR Automation Platform**. The full implementation - application code, database schema, tests and deployment configuration - lives in a **private repository** on this account, alongside the rest of the work shown here.

Source access can be arranged for hiring conversations, technical review or client due diligence. The quickest route is a short message on [LinkedIn](https://www.linkedin.com/in/muhammad-tanveer-advenno/) or an email to [mtanveertahir66@gmail.com](mailto:mtanveertahir66@gmail.com).

## About the engineer

**Muhammad Tanveer - Full-Stack AI Automation Engineer**

Full-stack AI automation engineer. I build agentic systems, browser and workflow automation, RAG pipelines and the production web platforms they run on - from Rust and Python services to Next.js dashboards and PHP/MySQL business systems.

- GitHub: [haddindeve](https://github.com/haddindeve)
- LinkedIn: [Muhammad Tanveer](https://www.linkedin.com/in/muhammad-tanveer-advenno/)
- Email: [mtanveertahir66@gmail.com](mailto:mtanveertahir66@gmail.com)
- Location: Pakistan

## Related projects

- [Salar Surgicals - Surgical Instruments Export Platform](https://github.com/haddindeve/salar-surgical-instruments)
- [Gym Management CRM with NFC Gate Control](https://github.com/haddindeve/gym-management-crm-system)
- [SMIP - Smart Manufacturing Intelligence Platform](https://github.com/haddindeve/smip-ai-iot-manufacturing-platform)
- [AuthentID - eMRTD Chip Identity Verification](https://github.com/haddindeve/authentid-emrtd-face-verification)
- [LinkedIn Lead Finder and Analyser](https://github.com/haddindeve/linkedin-lead-finder-and-analyser)
- [Exporter Lead Generator - AI B2B Buyer Discovery](https://github.com/haddindeve/exporter-lead-generator-ai)

---

<sub>Local Pulse - Google Maps CTR Automation Platform - case study by Muhammad Tanveer - Full-Stack AI Automation Engineer. Keywords: Google Maps ranking automation, local SEO automation, Playwright browser automation, CTR campaign platform, browser fleet orchestration, Next.js dashboard.</sub>