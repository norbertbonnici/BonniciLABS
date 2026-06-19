---
title: Switchboard
ref: SWB-03
category: APPLICATION
status: IN DEVELOPMENT
state: dev
order: 3
summary: One app where project tracking and the home-lab it runs on finally live together — a kanban board fused with live infrastructure management.
tags: swiftui · swiftdata · ios / macos
progress: 35
progress_label: BUILD
image: /assets/img/projects/switchboard.svg
image_alt: "Switchboard app icon"
stack: [SwiftUI, SwiftData]
platform: iOS 17 · macOS 14
year: 2026
meta_left: "store: swiftdata"
---

## The idea

Two boards I kept separately — a kanban for projects and an inventory of home-lab machines — really wanted to be one. Switchboard puts the work and the infrastructure that work runs on into a single place.

## What it does

- Kanban-style project tracking.
- A live inventory of home-lab hosts and services sitting right alongside it, so a task and the box it touches are never more than a glance apart.

## The build

Native **SwiftUI** with **SwiftData** for persistence, sharing one codebase across **iOS 17** and **macOS 14**.
