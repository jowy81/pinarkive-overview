# PinArkive

Distributed **IPFS-oriented storage and pinning platform** built around **IPFS clusters** (coordinated pinning and storage—not a single ad-hoc daemon). Users interact through a web application and APIs; **IPFS Cluster** and **IPFS (Kubo)** nodes provide storage and coordination. A **Node.js backend** fronts MongoDB and cluster APIs; supporting repos cover infrastructure, SDKs, CLI, examples, and public starter templates.

Built and maintained as part of real-world infrastructure and production environments.

> Public overview repository. Source code and production infrastructure are private.

## What it does

- Accepts uploads and **pins** content on IPFS, with orchestration paths that can use **Cluster API** or **Kubo** depending on operation and configuration (documented in private architecture material).
- Exposes a **versioned HTTP API** for programmatic access (exact routes and versioning are defined in private repositories).
- Persists **metadata and control-plane state** in **MongoDB** (including replica-set style layouts described in ops docs).
- Provides a **web dashboard** for operators and customers (React + Vite in the private frontend repo).
- Ships **SDKs** (e.g. TypeScript, with other language clients in the workspace) and a **CLI** for integration and automation.
- Maintains **infrastructure-as-code style** repositories for clusters and node images, plus compose-oriented runbooks for application stacks.
- Offers **public starter templates** (Next.js, Vite + Express, Cloudflare Workers + Hono) and a scaffold CLI so developers can experiment without embedding API keys in the browser.

## Why it exists

Teams need **reliable pinned IPFS content** with a real control plane—not only a single IPFS node. PinArkive separates **access** (web, SDKs, CLI), **control** (API + MongoDB), and **storage/orchestration** (cluster + Kubo nodes) so the system can be reasoned about, deployed, and debugged as a distributed product.

## Key Features

- Upload, pin, and lifecycle flows with documented failure modes in private ops documentation.
- **Multi-language SDKs** and shared TypeScript client patterns.
- **Optional workers** (email, expiry, cold storage) gated by feature flags in the private backend configuration model.
- **Internationalized** web UI (i18n stack present in the frontend dependency graph).
- **Charts and analytics-style** UI elements for usage visualization (private implementation).
- **Starter templates** that keep API keys on the server and demonstrate CID-returning uploads (public template collection alongside the core product repos).

## Architecture Overview

- **API / Backend** — Node.js (ESM), HTTP API, MongoDB, integrations with Cluster and Kubo clients.
- **Web** — React, Vite, TypeScript, Tailwind (Vite plugin), pnpm-based workflow in the private repo.
- **Data layer** — MongoDB for application metadata; IPFS for content-addressed blobs.
- **Storage / orchestration** — IPFS Cluster for coordination; Kubo nodes; dedicated infra repos for cluster topology and node deployment.
- **Access layer** — SDKs (TypeScript published packages and others), CLI, example applications, and landing/documentation sites (content is private unless published separately).
- **Automation / jobs** — Background workers for notifications and housekeeping (exact deployment topology is environment-specific and private).

## Tech Stack

Verified from private repositories (high level):

- **Backend:** Node.js, JavaScript modules, pnpm; Jest-based test scripts in the backend repo.
- **Frontend:** React 19, Vite, TypeScript, Tailwind CSS, Chart.js, i18next.
- **Data:** MongoDB.
- **Storage:** IPFS (Kubo), IPFS Cluster.
- **Templates (public-facing collection):** Next.js (App Router), Vite + React + Express, Hono on Cloudflare Workers; `npx`-style CLI for scaffolding.

## Current Status

**Private/internal project. Public details are intentionally limited.**

The product is a **distributed storage system** grounded in **IPFS and cluster orchestration**. This overview does **not** disclose topology, SLAs, regions, scale numbers, or infrastructure diagrams. Public starter templates may exist separately; they do not imply disclosure of production layout.

## Screenshots / Demo

<!--
Add screenshots or GIFs here:
![Demo](./assets/demo.gif)
-->

## Notes

This repository is a public overview only. The source code, cluster topology, credentials, internal domains, and production runbooks are not exposed. References to public marketing or documentation sites are omitted here to keep this page vendor-neutral and NDA-safe.

## Contact

LinkedIn:  
https://www.linkedin.com/in/joel-domenech/
