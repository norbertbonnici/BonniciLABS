---
title: StrataDFIR
ref: STR-01
category: APPLICATION
status: IN DEVELOPMENT
state: dev
order: 1
featured: true
summary: An on-device forensics workbench for macOS & iOS — The Sleuth Kit for the parsing, Apple's Foundation Models for the analysis, and nothing ever leaves the machine.
tags: swiftui · the sleuth kit · foundation models · macos / ios
progress: 68
progress_label: BUILD
stack: [SwiftUI, The Sleuth Kit, Foundation Models, Swift]
platform: macOS · iOS
image: /assets/img/projects/stratadfir.svg
image_alt: "StrataDFIR app icon"
year: 2026
meta_left: "analysis_mode: local"
# repo: https://github.com/norbertbonnici/...
---

## The problem

Cloud LLMs are off the table for a lot of forensic work. When you're handling evidence under data-sovereignty rules — or simply working a case on an air-gapped machine — you can't ship artifacts off to someone else's API. But the fast pattern-matching that makes large language models useful for triage is exactly what you want when you're staring at a fresh disk image.

## What it is

StrataDFIR is a digital-forensics workbench for macOS and iPadOS. It sits on top of **The Sleuth Kit** for the low-level file-system and artifact work, wraps it in a native **SwiftUI** interface, and adds an analysis layer built on **Apple's Foundation Models** framework — so the model runs on the same machine doing the examination. The case never touches the network.

## How it works

- **The Sleuth Kit** handles volume and file-system walking, deleted-file recovery, and artifact extraction.
- A **SwiftUI** front-end presents the case, the file tree, and parsed artifacts as a proper Mac / iPad app rather than a terminal session.
- **Foundation Models** provide on-device, LLM-assisted interpretation — summarising artifacts, surfacing leads, and answering plain-language questions about what's on disk, with no round-trip to a server.

## Architecture

Built for the single-analyst, single-Mac case first. 

## Status

In active development. Recent work includes a full UI / UX pass and a Swift hand-off package. A talk on the approach — *Air-Gapped Analyst: On-Device LLM Forensics with StrataDFIR* — is proposed for LABScon 2026.
