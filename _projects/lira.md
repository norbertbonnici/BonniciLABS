---
title: Lira
ref: LIR-02
category: APPLICATION
status: LIVE
state: live
order: 2
summary: Self-hosted personal finance as a single static Go binary over SQLite, with TOTP two-factor. Named after the old Maltese lira.
tags: go · sqlite · self-hosted · totp
stack: [Go, SQLite, Cloudflare Tunnel]
platform: Self-hosted · Linux
year: 2026
image: /assets/img/projects/lira.svg
image_alt: "Lira app icon"
meta_left: "build: single_binary"
repo: https://github.com/norbertbonnici/Lira
---

## Why

I wanted my financial data on my own hardware, not sitting in someone else's SaaS. Lira is the result: a small, fast finance tracker I actually own and run myself.

## The build

The whole thing compiles to a **single static Go binary** over **SQLite** — no runtime to install, no external database, no container required. Copy one file, run it. As it grew it went through a full MVC refactor to keep the code honest.

## Running it

Lira lives on a ZimaBoard (Proxmox / Ubuntu) and is reachable through a **Cloudflare tunnel**, with **TOTP** two-factor on the way in. Small footprint, low maintenance, mine.

## The name

*Lira* is the Maltese lira — the island's currency right up until the euro changeover in 2008. A fitting name for a money app built in Malta.
