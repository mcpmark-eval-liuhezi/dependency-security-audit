# npm Advisory Watchlist

Quarterly dependency security review for our Node services. Source: GitHub Global Security Advisory Database (npm ecosystem).

Lookups run 2026-10-15: first page of **critical**-severity npm advisories, and separately the first page of **high**-severity npm advisories.

## Watchlist

| GHSA ID | Severity | Affected package | First patched version |
| --- | --- | --- | --- |
| GHSA-qx66-fv34-fjm8 &#9888;&#65039; **MOST URGENT** | Critical | `@tanstack/start-server-core` (also `@tanstack/react-start`, `@tanstack/solid-start`, `@tanstack/vue-start`) | `1.169.39` (react-start `1.168.60`, solid-start `1.168.57`, vue-start `1.168.56`) |
| GHSA-x34j-47hf-4xg7 | Critical | `tinacms` / `@tinacms/app` | No patched release confirmed — advisory states tested `tinacms@3.12.1` / `@tinacms/app@2.5.12` remain vulnerable and gives ranges as `<=` |
| GHSA-pq7j-f95f-qfcv | High | `@anthropic-ai/claude-code` | `2.1.179` |
| GHSA-x586-xvc8-g7q6 | High | `@builder.io/qwik` (also `@qwik.dev/core`) | `1.20.0` (`@qwik.dev/core` `2.0.0-beta37`) |
| GHSA-2vc4-c4r6-p6v6 | High | `@opennextjs/cloudflare` | `1.20.2` |

## Most urgent advisory

**GHSA-qx66-fv34-fjm8 — TanStack Router: Unauthenticated reflected XSS in TanStack Start server-function responses**

- GHSA ID: `GHSA-qx66-fv34-fjm8`
- CVE: `CVE-2026-102989`
- Severity: Critical (CVSS 9.3, `CVSS:3.1/AV:N/AC:L/PR:N/UI:R/S:C/C:H/I:H/A:N`)
- Published: 2026-10-15T20:22:20Z (updated 2026-10-15T20:22:22Z)
- Affected packages and first patched versions:
  - `@tanstack/start-server-core` — `>= 1.143.12, < 1.169.39` — first patched **1.169.39**
  - `@tanstack/react-start` — `>= 1.143.12, < 1.168.60` — first patched 1.168.60
  - `@tanstack/solid-start` — `>= 1.143.12, < 1.168.57` — first patched 1.168.57
  - `@tanstack/vue-start` — `>= 1.143.12, < 1.168.56` — first patched 1.168.56

Impact: an unauthenticated attacker can craft a URL to a server function in an affected TanStack Start app. If someone opens the link, the app can return attacker-controlled HTML from its own origin and run attacker JavaScript there, with access to same-origin data and the visitor's authority.

## Maintainer

The affected packages are maintained by the **TanStack** GitHub organization — login `TanStack`, https://github.com/TanStack. The advisory's source of record is the [TanStack/router](https://github.com/TanStack/router) repository.

## Fix tag

Release tag that first contains the fix, in the `TanStack/router` repository:

- Tag name: `release-2026-09-30-1747`
- Points to commit: `57e126e99dbd86f735ead2ba98ba5e98ef0cc668`
- Tagged 2026-09-30T17:47:25Z by `github-actions[bot]` (unsigned)

The advisory references also cite fix commit `d521abd71c69f1ff010bb3def4d417cb5fa058cb` (TanStack/router PR #8573).
