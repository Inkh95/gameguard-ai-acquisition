# GameGuard AI — Poker Integrity Review Prototype

**Self-hosted review aid for online poker platforms. Source available for one-time acquisition.**

GameGuard AI accepts normalized decision telemetry and returns review cases with interpretable signals. Its intended user is a game-integrity analyst. It does not automatically penalize players and does not claim to prove AI or solver assistance.

![Synthetic review console example](demo.svg)

## What runs today

- Authenticated HTTP analysis API with structured JSON results.
- Interactive local review console for uploading a normalized decision JSON file and inspecting evidence.
- CSV adapter for exports with the documented event fields.
- Four signal families: unusually consistent decision times; rapid decisions; unusually long observed sessions; high consistency in comparable, operator-defined spots; plus shared device pseudonyms.
- Python standard library implementation, Dockerfile, synthetic demo generator, 16 passing automated tests, source and handoff documentation.
- No hosted AI provider dependency and no seller-run subscription.

## Sample output from the included synthetic fixture

| Synthetic profile | Decisions | Heuristic priority score | Workflow status | Flagged signals |
|---|---:|---:|---|---|
| Randomized timing/actions | 180 | 0/100 | Monitor | None |
| Scripted timing/actions | 180 | 45/100 | Review | Low timing variation; repeated-spot consistency |

This demonstration is **seller-authored synthetic data**, not a benchmark of real-world detection quality. Scores represent review priority, not confidence or probability of cheating. Legitimate behavior and logging artifacts can cause alerts.

## Integration contract

`POST /v1/analyze` takes an array of pseudonymous decision events: event, player, session and hand identifiers; action; timestamp; and decision latency. Operator-defined spot keys and device pseudonyms are optional. It returns per-player status, scores, observed values, sample counts, and explanations. No player data are stored by the prototype. A buyer would run and validate the service on its own infrastructure behind a TLS and access-control gateway.

## Acquisition inquiry

The full prototype source, tests, demo, deployment files and handoff notes are available for a proposed **€5,000 one-time source acquisition**, subject to technical diligence and agreed written transfer terms. This is an asking price, not a verified valuation. No real-world detection precision, recall, compliance certification or production integration is claimed.

Contact the owner via [GitHub profile](https://github.com/Inkh95). Request a supervised API demonstration and technical overview. The private source is not published here.

### Scope and buyer validation

The current version is a poker telemetry triage prototype. It does not parse proprietary hand histories without an adapter, score blackjack, implement solver comparison, infer guilt, or provide a persistent case-management database. An operator should validate it on consented, labelled data before operational use. Its present value is the inspectable architecture and handoff-ready working foundation.
