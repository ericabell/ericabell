# Eric Abell

Software engineer building production apps with Claude Code · Python / Django / React · Austin, TX

I run [EAltitude](https://ealtitude.org), a one-person software and security consultancy, and build and operate production web apps for paying clients, from scoping and architecture through deployment and ongoing support. I got here by an unusual route: electrical engineer at Motorola and Freescale, seven years teaching AP Calculus, then full-stack work at Vectra AI and InnoVetted. Most of my client work is private, so this page describes it instead of linking to it.

## How I work with Claude Code

Claude Code is my primary development tool. The practice around it matters more than the tool:

- **Plan first.** Every change starts as a written plan (current state, what changes and why, files affected) that I approve before any code is touched.
- **Branch and review.** Work happens on a branch, and I review the full diff before merging. AI-generated code never ships unexamined.
- **Deliberate context.** CLAUDE.md files carry each project's conventions and architecture, and my shared conventions cover domain modeling, logging, testing and "keep the exit cheap" library choices.
- **Custom tooling.** Skills for recurring work (parsers, changelogs, commits, worklogs, blog posts), hooks, and MCP servers, including a time-tracking server I wrote that logs sessions, ties them to Linear tickets and git commits, and produces monthly invoice reports.
- **Tests on everything.** Agents write tests alongside the code, and the suite decides whether a change is done.

## Featured work

The code for these is private. I'm happy to walk through the architecture.

### ModernQR: multi-tenant clinic platform

[modernqr.scalenelabs.com](https://modernqr.scalenelabs.com)

I took over ModernQR and rebuilt it end to end. It now serves about 20 paying clinics, mostly solo practitioners, all found through word of mouth, and has been in production for 18 months.

- QR-code patient check-in, appointment scheduling, Stripe billing, Twilio SMS (about 1,000 patient messages a month), JWT authentication, scheduled lifecycle jobs
- Django REST Framework backend, React/Vite/Material-UI frontend, Dockerized deployment
- 400+ backend tests plus Playwright end-to-end tests, release-branch workflow

### Traffic-analysis platform for a civil-engineering firm

Replaced a multi-day, error-prone process of copying traffic-model (Synchro/HCM) results into Excel with a platform that generates engineering reports in about 30 seconds and scales smoothly with input volume.

- Parser for traffic-model output feeding an asynchronous Django REST Framework + Celery/Redis pipeline
- React/Vite/Tailwind frontend, encrypted file handling
- Docker behind Traefik on Ansible-provisioned, hardened servers

## Side projects

Things I build for myself, mostly at the intersection of data, hardware and the outdoors:

- **SweatDown:** native SwiftUI iOS app that connects to gym cardio machines over Bluetooth LE (the FTMS profile), records workouts and analyzes them on-device.
- **Apple Health Explorer:** turns full-history Apple Health exports into a queryable DuckDB database, with incremental ingestion so each new export adds only genuinely new records.
- **Home Telemetry:** a utility-usage database for electric, water and gas, recovered from customer portals with no documented API, alongside weather and irrigation data that explain the consumption.
- **SHT45 logger:** an ESP32 Feather reads a temperature/humidity sensor every 60 seconds and posts to a collector that persists to SQLite.
- **GPS tracker:** Raspberry Pi GPS tracking for equipment in the field, backed by an AWS-hosted Django GeoSpatial database.
- **Math worksheet toolkit:** a Typst library and CLI for generating student math worksheets (Algebra 1 through Calculus) with Claude Code, and for recreating existing PDF worksheets as editable source.
- **Blog toolchain:** write posts in Markdown, render them to clean HTML that pastes straight into Medium.

## Elsewhere

- Writing: [medium.com/@eric_abell](https://medium.com/@eric_abell)
- LinkedIn: [linkedin.com/in/eric-a-7364aa11a](https://www.linkedin.com/in/eric-a-7364aa11a/)
