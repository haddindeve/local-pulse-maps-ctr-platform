# Local Pulse - Google Maps CTR Automation Platform - case study

**Engineer:** Muhammad Tanveer - Full-Stack AI Automation Engineer  
**Repository:** https://github.com/haddindeve/local-pulse-maps-ctr-platform

## Context

Local-ranking campaigns meant an operator manually driving dozens of browser profiles, with no shared record of what ran, from which profile, or what happened afterwards. Work was unrepeatable and impossible to audit across clients.

## What I built

Two cooperating processes in one repository: a Next.js dashboard as the command centre, and a Node/Express + Playwright backend that drives a fleet of isolated browser profiles on a Linux VPS. The dashboard talks to the live backend over a typed API layer; campaigns, workers and results are persisted so every run is reproducible and attributable.

## Capabilities delivered

- Campaign control plane for Maps local-ranking work
- Playwright fleet with per-profile isolation
- Search and referral flow engine
- Multi-tenant separation for agency use
- Deployment runbook for reproducible VPS setup

## Outcome

- Manual browser driving replaced by queued, auditable campaign runs
- Every run attributable to a campaign, profile and result set
- Backend bound to loopback and fronted by the dashboard, keeping automation off the public internet

## Source

The implementation is held in a private repository. Access can be arranged on request - [mtanveertahir66@gmail.com](mailto:mtanveertahir66@gmail.com) or [LinkedIn](https://www.linkedin.com/in/muhammad-tanveer-advenno/).