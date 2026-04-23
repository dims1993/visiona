# Visiona

Plan and publish social content (Instagram, TikTok, Facebook) from your own media library—with templates and light visual consistency—without spending hours in the workflow.

---

## The heart of the app

This paragraph is the **product north star**; detailed rationale lives in [docs/ARCHITECTURE.md](./docs/ARCHITECTURE.md).

> This project aims to build an app that lets users create content for Instagram, TikTok, and Facebook using a library of images or short videos they upload. The goal is for users to schedule content for their web presence in **few clicks** without spending much time. We may rely on **templates** to keep visual coherence across posts and **light filters** or color alignment so the feed feels **homogeneous**.

---

## Engineering principles

- **Commits**: Every implemented change is committed with a message **in English** (project convention).
- **README**: Update this file for **meaningful** product or engineering milestones—not for minor visual-only tweaks. Deep technical structure and stack rationale stay in [docs/ARCHITECTURE.md](./docs/ARCHITECTURE.md) unless we fold a summary here after major pivots.

---

## Architecture at a glance

| Area | Direction |
|------|-----------|
| App shell | Next.js (React), TypeScript |
| Data | PostgreSQL for metadata and schedules; S3-compatible storage for media |
| Async work | Job queue for transcoding, color pipelines, and **scheduled publishing** |
| Social | Official/platform APIs with OAuth; adapters per network |

**Why this shape:** a modular monolith keeps delivery fast while we prove the UX; workers isolate slow and failure-prone work (video, publishing retries). See the full blueprint in [docs/ARCHITECTURE.md](./docs/ARCHITECTURE.md) for folder layout, phases, and open decisions (ORM, auth provider, job system).

---

## Current status

Repository bootstrap: architecture and conventions documented; application code not yet scaffolded.

---

## License

TBD.
