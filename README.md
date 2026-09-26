# GameGuard AI — Poker Integrity Review Prototype

**For poker operators and integrity teams.** A self-hosted v0.5 prototype that turns poker decision telemetry into analyst review cases with interpretable signals and hand references. It supports human review; it does not prove AI/solver use, measure cheating probability, or sanction players automatically.

[Illustrative synthetic result](demo.svg) · [Demonstration walkthrough](DEMO.md) · [Български преглед](OVERVIEW_BG.md)

> **This repository is a buyer showroom, not a live application.** The source and runnable console are private. Request a supervised technical demonstration and code review.

## Analyst workflow

1. Import supported CSV or a limited subset of English PokerStars Hold'em text histories. Player and table names are pseudonymized locally with an operator-provided key.
2. Analyze decisions through a token-authenticated API. Review cases in a local browser console with filters, per-hand traces and JSON/CSV export.
3. Have an integrity analyst inspect the evidence and missing data before deciding whether further investigation is appropriate.

![Two synthetic profiles; illustrative only](demo.svg)

| Seller-authored synthetic profile | Decisions / hands | Review priority | Observation |
| --- | ---: | ---: | --- |
| Varied timing/actions | 180 / 180 | 0/100 · Monitor | No triggered signals in this fixture |
| Scripted timing/actions | 180 / 180 | 45/100 · Review | Low timing variation and repeated-spot consistency |

**The scores are review priorities, not probabilities of misconduct.** These synthetic fixtures cannot establish detection accuracy, sensitivity or false-positive rates. Legitimate behavior and logging artifacts can create alerts.

## Implemented scope reported for v0.5

- Five heuristic signal types covering timing, repeated operator-defined decision contexts, session duration and shared device pseudonyms. Missing timing, spot or device fields are reported rather than invented.
- Descriptive action counts by betting street, hand references, CSV import, JSON/CSV report export, Dockerfile and handoff instructions.
- Synthetic fixtures and **29 passing tests reported for the private source**. They cannot be reproduced from this public repository. The independent-label evaluation command needs real reviewed labels.
- No seller-hosted backend, subscription or hosted AI dependency.

## Evidence and limitations

| Available evidence | Supports | Does not establish |
| --- | --- | --- |
| [Synthetic example](demo.svg) | Explains a review priority and intended workflow | Real-world fraud detection performance |
| 15 older public PokerStars histories, 181 actions | A limited parser check | Compatibility with a current operator export or detection of AI/RTA |
| Internally reported tests | Development regression coverage | Independent audit or production readiness |

Ordinary text hand histories contain actions and hand-start times, but generally no per-decision reaction times. The parser does not invent them. All 73 player IDs in the external 15-hand sample have insufficient data and no misconduct labels. Hand-history-only analysis may provide no actionable RTA flag; operator event telemetry is needed for timing and richer context.

This build has no solver comparison, blackjack module, persistent case database or production certification. Docker build was not run in the seller's environment; the private source includes a Docker verification script. Direct HTTP startup and authenticated analysis were checked internally. See the [demonstration and shadow-mode pilot plan](DEMO.md).

## Commercial options

| Option | Asking price | Scope |
| --- | ---: | --- |
| [Organization source license on Payhip](https://payhip.com/b/gnjbC) | €790 | Non-exclusive license for one legal organization under the included LICENSE.md; downloadable source, tests, synthetic demo, Dockerfile and handoff notes. Applicable taxes at checkout. |
| Project/IP acquisition discussion | €5,000 | Proposed one-time transfer subject to technical diligence, prior non-exclusive licenses and written terms. |

No hosting, integration, support, future updates or validated detection performance is included by default. The acquisition amount is an asking price, not a verified market valuation.

**Next step:** [Contact the owner on GitHub](https://github.com/Inkh95) to arrange a supervised demonstration or discuss a shadow-mode pilot using authorized, anonymized and independently reviewed operator data. No player action should be based on an unvalidated score.
