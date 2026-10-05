---
title: Mina
ref: MIN-04
category: PLATFORM
status: IN DEVELOPMENT
state: dev
order: 4
summary: Organisation-controlled secure internet research egress — analysts browse from a locked-down Edge profile whose traffic leaves through governed Azure EU addresses instead of the organisation's own. Attribution separation, not anonymity.
tags: .net · envoy · mtls · azure · intune · wazuh
progress: 80
progress_label: BUILD
stack: [.NET, Envoy, SQL Server, Terraform, Azure]
platform: Windows 11 endpoint · on-prem control plane · Azure egress
year: 2026
image: /assets/img/projects/mina.svg
image_alt: "Mina icon — a tunnel portal with a light at its far end"
meta_left: "mode: fail_closed"
repo: https://github.com/norbertbonnici/Mina
---

## The problem

Analysts in regulated organisations research the open internet every day, and every request leaves from the organisation's fixed public IPs. That is a problem on both sides: targets can attribute the research to the organisation, and the organisation cannot cleanly govern or audit which traffic was research at all. A consumer VPN solves neither. An open proxy makes things worse.

## What it is

Mina is a governed egress platform. An authorised analyst gets a dedicated **research Edge profile** on a managed Windows 11 endpoint. Only that profile talks to a local **Mina agent**, which carries the traffic over an **mTLS tunnel** to an **Envoy** egress stamp in an approved Azure EU region, where it exits through static NAT addresses. Everything else on the machine keeps using normal corporate egress, unchanged.

The point is **attribution separation under governance** — sessions are requested, approved, time-boxed and logged. It is explicitly not anonymity, not a corporate VPN and never an open proxy.

## How it works

- **Endpoint** — Intune-managed Windows 11. The agent is a loopback proxy enforced with WFP rules against a distinct research-browser image path. If the agent, the session or the tunnel disappears, that profile has no route out at all.
- **Control plane** — runs on premises on a Proxmox cluster in the DMZ: an API, a management UI for approvals, regions and audit, and SQL Server behind it. Entra ID supplies identity, Conditional Access and device compliance.
- **Egress stamps** — one per approved EU region: Envoy terminating mTLS and HTTP/2 CONNECT in front of a NAT Gateway with static egress IPs. The stamps have no path back into the organisation.
- **Telemetry** — hostname-level URL telemetry without TLS interception. Security and audit events go to Wazuh, operational telemetry to SigNoz, and the CA key and audit anchors live in Azure Key Vault and immutable blob storage.

## Design record

The repository carries the real design documents rather than a rewritten version for publication: a threat model, a privacy analysis, the Phase 0 decision log, architecture decision records and a security review. All twelve Phase 0 decisions are closed, including the choice of hostname telemetry over TLS interception and the move of the control plane from Azure to on premises.

## Status

Phase 0 is complete and milestones M0 to M3 are built. M4 hardening is in progress: the region-activation drill, patch cadence, break-glass procedure, an external penetration test and the final acceptance-evidence bundle still stand between the current build and a production go/no-go. There is no tagged release yet.

## Running the demo

```bash
MINA_ENVOY=/path/to/envoy dotnet run --project demo/Mina.Demo -c Release
```

Runs the control plane, a real Envoy egress and the agent in one process, exposes a proxy port a browser can use, and lets you press `k` to watch the protected path fail closed.

## Licence

Apache 2.0.
