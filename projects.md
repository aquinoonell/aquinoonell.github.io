---
layout: page
title: Projects
permalink: /projects/
---

# [zero2prod](https://github.com/aquinoonell/zero2prod)

*Newsletter API following Luca Palmieri's Zero to Production in Rust*

- Actix Web HTTP API with `GET /health_check` and `POST /subscriptions` (urlencoded form to email/name), exposed through a reusable `run(TcpListener)` entrypoint shared by the binary and tests
- Black box integration tests that spawn the real server on an ephemeral port and assert health, happy path subscribe (`200`), and missing field validation (`400`) over HTTP
- Postgres domain model via sqlx migrations (`subscriptions` with uuid, unique email, name, `subscribed_at`) plus a Docker bootstrap script for create/migrate
- GitHub Actions quality gates: `cargo test`, rustfmt, clippy (`-D warnings`), Tarpaulin coverage, and scheduled `cargo deny` advisory audits

# [Bronx Special Kids](https://bronxspecialkids.org/)

*Jun 2026 - Present*

Production WordPress site for a parent led 501(c)(3) supporting neurodivergent children in the Bronx. Operated on Hostinger over SSH for deploys, recovery, and production config.

- Migrated the public site from a WoodMart e commerce demo stack to a nonprofit architecture with live pages for Home, About, Programs, Resources, Volunteer, Consulting, Contact, and Donate
- Custom PHP plugin (`bronxspecialkids-nonprofit`) modularized for donations, volunteers, contact forms, compliance/legal pages, payments setup, resources, PDF viewer, and UI components
- WooCommerce + WooPayments donation flow with amount presets, 501(c)(3) checkout disclosures, and branded thank you receipts
- Accessibility minded front end (skip links, focus styles, semantic markup), bilingual Spanish services callouts, cookie/privacy surfaces, and Hostinger SSH based deploy/ops

# [Ray Tracer](https://github.com/aquinoonell/Ray-Tracer)

*Mar 2026 - Present*

Physically based renderer written from scratch in Rust, following *Ray Tracing in One Weekend* with *The Ray Tracing Road to Rust*.

- From scratch 3D math (`Vec3` / `Point3` / `Ray`) and a trait based scene graph (`Hittable`, `HittableList`, spheres)
- Materials: Lambertian diffuse, metal with fuzz, dielectric glass with Schlick reflectance; thin lens camera for depth of field
- Multi sample antialiasing (500 spp), recursive bounces (depth 50), gamma correct PPM output
- Parallel pixel loop with Rayon: about 90 minutes single threaded to about 30 minutes on a 1200x800 image

# Language Analytics / LenguaForge

*Dec 2025 - Feb 2026*

Team product for language assessment (React + AWS). Contributions spanned meeting capture, invites, analytics UI, and infra.

- Google Meet recording path: Playwright bot that joins Meet, captures chunked audio, tracks speakers, uploads to S3; Terraform for ECS/ECR/CodeBuild/API Gateway plus an EC2 instant join path to cut cold starts
- Sole author of the Manifest V3 Chrome extension: `tabCapture` + offscreen `MediaRecorder`, WebSocket streaming, speaker detection, Auth0 token handoff, EN/ES i18n
- Teacher student invitation system end to end: DynamoDB APIs, secure tokens, email delivery, React invite/signup UX
- Learning analytics UI (Recharts progression, report cards, language badges) and async report status polling with notifications for completed/failed transcriptions

# [Lakebridge](https://github.com/aquinoonell/Lakebridge)

*Postgres cold data archive with DataFusion SQL federation*

- Archives aged PostgreSQL rows to partitioned Parquet while keeping historical data queryable
- Federates live Postgres + cold Parquet through a single DataFusion SQL interface (`sync` / `query` CLI)
- Aimed at lean OLTP without standing up a separate warehouse/Kafka/Spark stack

# AI Hub

*Case study (source private)*

Local macOS dashboard and CLI for switching Claude Code / ChatGPT accounts with project context handoff.

- Persists an explicit handoff (`AGENT.md`, `context.md`, git snapshot) and launches the next account in an isolated config/profile
- Rust service with Axum, SQLite, clap CLI, and macOS Keychain integration

# [Tuxedo](https://github.com/webstonehq/tuxedo)

*Open source contributor*

Keyboard driven terminal UI for todo.txt.

- Merged [#114](https://github.com/webstonehq/tuxedo/pull/114): config hot reload watcher lifetime fix
- Merged [#117](https://github.com/webstonehq/tuxedo/pull/117): cursor row visibility regression in the task list UI
