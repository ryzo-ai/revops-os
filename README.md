```
 ____    ____    __  __  _____   ____    ____         _____   ____
/\  _`\ /\  _`\ /\ \/\ \/\  __`\/\  _`\ /\  _`\      /\  __`\/\  _`\
\ \ \L\ \ \ \L\_\ \ \ \ \ \ \/\ \ \ \L\ \ \,\L\_\    \ \ \/\ \ \,\L\_\
 \ \ ,  /\ \  _\L\ \ \ \ \ \ \ \ \ \ ,__/\/_\__ \     \ \ \ \ \/_\__ \
  \ \ \\ \\ \ \L\ \ \ \_/ \ \ \_\ \ \ \/   /\ \L\ \  __\ \ \_\ \/\ \L\ \
   \ \_\ \_\ \____/\ `\___/\ \_____\ \_\   \ `\____\/\_\\ \_____\ `\____\
    \/_/\/ /\/___/  `\/__/  \/_____/\/_/    \/_____/\/_/ \/_____/\/_____/
```

> **Ryzo's RevOps operating system** — open-sourced as a Claude Code plugin.

[![Claude Code Ready](https://img.shields.io/badge/Claude_Code-ready-5A45FF)](https://claude.com/claude-code)
[![Skills](https://img.shields.io/badge/skills-16-E0621A)](#skills)
[![License: MIT](https://img.shields.io/badge/license-MIT-3DA639)](LICENSE)

Sixteen skills spanning the full RevOps surface — lifecycle, scoring, routing, pipeline, automation, hygiene, dashboards, attribution, forecasting — plus a 5-skill delivery workflow (6 stages; implement covers 3–4) that takes a CRM from audit to a coached, self-sufficient team.

## Install

**As a plugin (recommended):**
```
/plugin marketplace add ryzo-ai/ryzo
/plugin install revops-os@ryzo
```

**As plain skills (copy-in):**
```
git clone https://github.com/ryzo-ai/revops-os
cp -r revops-os/skills/* ~/.claude/skills/
```

## Quick start

Once installed, drive it in plain language — each skill auto-triggers on the right ask. A full engagement reads like a conversation:

1. *"Audit our CRM"* → **revops-audit** systematically assesses the current state and produces a prioritized findings report.
2. *"Design our lifecycle stages and lead scoring"* → **lifecycle-stages** defines the MQL/SQL handoff; **lead-scoring** builds the fit + engagement model.
3. *"Where do our deals actually come from?"* → **attribution** attributes pipeline and revenue to the channels that actually produced it.
4. *"Build me a forecast"* → **forecasting** sets up coverage ratios, forecast categories, and a defensible number.
5. *"Blueprint then implement it"* → **revops-blueprint** designs the solution as a client-approvable contract; **revops-implement** configures HubSpot or Attio to match it.

Later in the engagement: **revops-optimize** tunes the live system against real performance data, and **revops-coach** builds the training materials that hand it off to the client's team.

## Skills

Three layers, sixteen skills:

- **Router (1):** **revops** — entry point that routes a RevOps ask to the right capability skill.
- **Capability (10):** **lifecycle-stages**, **lead-scoring**, **lead-routing**, **pipeline-management**, **crm-automation**, **deal-desk**, **data-hygiene**, **revops-dashboards**, **attribution**, **forecasting** — the building blocks of a RevOps system, each usable standalone.
- **Delivery (5):** **revops-audit** → **revops-blueprint** → **revops-implement** → **revops-optimize** → **revops-coach** — Ryzo's own 5-skill delivery workflow (6 stages; implement covers 3–4), from assessment through hands-off enablement.

## Prerequisites

- A CRM — HubSpot or Attio. Bring your own; no keys ship in this repo, and none
  are stored in any skill file. Credentials are supplied via environment
  variables or your CRM's MCP/API integration.

## Why we open-sourced it

This is the actual RevOps system we run for clients — not a demo. We publish it because good RevOps playbooks compound in the open: markdown-native (no lock-in), version-controlled, and forkable. Take it, adapt it to your CRM and team, and ship a RevOps system that actually holds up. If it helps, [tell us](https://ryzo.nl).

## About

Built by [Ryzo](https://ryzo.nl) — the AI-native GTM & RevOps agency. This is the real RevOS methodology we run for clients, genericized for open use. MIT licensed.
