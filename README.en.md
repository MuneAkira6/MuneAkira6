# So Ryo

[日本語](README.md)

Full-stack engineer on a multi-tenant B2B SaaS. I started on the frontend (React / TypeScript) and now
also work on the backend (Scala / Play / Akka, MongoDB), test automation and CI.

AI agents (Claude Code) write most of the code; I own the design, the rulings and the verification.
The repositories here rebuild, in a form that can be published, the methods I use in that work.

## What I have worked on

| Area | What | Figures from the job (code not public) | Case study · demo |
|---|---|---|---|
| Platform integration | Integrating a group-wide account and tenant platform: authorization code + PKCE, platform Bearer tokens on existing APIs, role derivation, signed webhooks, tenant sync — all behind default-off settings | 18 merged PRs (Aug–Sep 2026) | [Case 01](https://github.com/MuneAkira6/engineering-case-studies/blob/main/01-platform-integration.md) · [idp-tenant-integration-demo](https://github.com/MuneAkira6/idp-tenant-integration-demo) |
| Test automation | A coverage ledger whose denominator is the functional spec, and a quality gate that tells four kinds of red apart (new, declared, inconclusive, went green) | UI coverage 22.1% → 83.9% (including existing QA assets) | [Case 02](https://github.com/MuneAkira6/engineering-case-studies/blob/main/02-test-automation-and-quality-gates.md) · [regression-gate-demo](https://github.com/MuneAkira6/regression-gate-demo) |
| CI and developer experience | PR compile checks on a self-hosted runner, tracing non-deterministic build failures, devcontainer I/O, an automated OSS license inventory | PR compile check in about 3 minutes, no hosted minutes used | [Case 03](https://github.com/MuneAkira6/engineering-case-studies/blob/main/03-ci-and-developer-experience.md) · [ci-devex-toolkit](https://github.com/MuneAkira6/ci-devex-toolkit) |
| AI agents | The long-lived bus with unattended goals, and spec-driven development with spec-kit | 18 bus runs, longest unattended stretch 16 h 37 min; 46 spec folders | [Case 04](https://github.com/MuneAkira6/engineering-case-studies/blob/main/04-unattended-goal-bus.md) · [Case 05](https://github.com/MuneAkira6/engineering-case-studies/blob/main/05-spec-driven-development.md) |

## Two methods

- **Long-lived bus + unattended goals** ([goal-bus-kit](https://github.com/MuneAkira6/goal-bus-kit)): a worker
  session executes goals; a long-lived "bus" session, the one that wrote the goal pack, reviews every goal
  boundary and writes the next goal's instructions; two Stop hooks drive the loop by reading files, not
  conversation.
- **Spec-driven development** ([spec-driven-dev-playbook](https://github.com/MuneAkira6/spec-driven-dev-playbook)):
  the spec folder is the requirement, a human rules on every clarification one by one, and every verdict is
  PASS, FAIL, BLOCKED or DEFERRED with its evidence.

Four repositories of this portfolio were themselves built by unattended bus runs from a contract written first
(221 verdict rows over four runs, no human intervention — figures from the demos).

## Repositories

| Repository | What it is |
|---|---|
| [goal-bus-kit](https://github.com/MuneAkira6/goal-bus-kit) | A toolkit to add the bus method to any repository: hooks, self-tests, templates, 30 lessons, a recorded run |
| [spec-driven-dev-playbook](https://github.com/MuneAkira6/spec-driven-dev-playbook) | A spec-driven development guide (in Japanese) and ten fill-in templates |
| [idp-tenant-integration-demo](https://github.com/MuneAkira6/idp-tenant-integration-demo) | A runnable demo of adding IdP sign-in to an existing SaaS, with its full spec folder and the record of its unattended build |
| [regression-gate-demo](https://github.com/MuneAkira6/regression-gate-demo) | A Playwright regression suite, coverage against the manual test sheet, and a four-class quality gate |
| [ci-devex-toolkit](https://github.com/MuneAkira6/ci-devex-toolkit) | An OSS license inventory, a two-repositories-one-worktree helper, a PR compile check, a devcontainer I/O harness |
| [engineering-case-studies](https://github.com/MuneAkira6/engineering-case-studies) | Seven case studies of the work above (in Japanese) |

## Scale of the job

161 merged pull requests and 92 pull requests of others reviewed (Oct 2025 – Sep 2026; figures from the job).

## About the numbers

Figures from the job are marked as such (the code is not public). Figures from the demos come only from
running those repositories. The two are never mixed in one table.

## Technologies

TypeScript · React · Node.js · Scala · Play Framework · Akka · MongoDB · Playwright · Vitest ·
GitHub Actions · Docker · Keycloak · Claude Code

## Languages

Japanese (JLPT N1) · Chinese (native) · English (reading, writing and conversation)

---

Design, review and verification: So Ryo / Implementation: in collaboration with an AI agent (Claude Code)
