# GameGuard AI — demonstration walkthrough

This is a **guide to a supervised demonstration**, not proof of real-world detection performance. The [interactive replay](https://inkh95.github.io/gameguard-ai-acquisition/) lets you inspect a reduced projection of the [generated synthetic report](synthetic_report.json); it does not run the engine. A local rerun passed 29/29 tests; see [verification notes](EVIDENCE.md). The [public image](demo.svg) shows two seller-authored synthetic profiles; their scores are review priorities, not probabilities.

## Five-minute technical walkthrough

1. **Input and coverage.** Show synthetic decisions with hand references and, where available, event timestamps and operator-defined context. Identify absent fields. A text hand history alone does not contain per-decision reaction times.
2. **Import.** Run the private importer locally and compare parsed actions with source hands. Show local pseudonymization. The 15 older public histories, 181 actions, check only limited parser behavior.
3. **Analysis.** Submit the synthetic decisions to the token-authenticated API. In the browser console show both 180-decision profiles and review priorities 0/100 and 45/100.
4. **Evidence review.** Open a case, follow signal explanations to referenced hands, and demonstrate missing-data notices, filters and JSON/CSV export.
5. **Limits.** Explain that legitimate play or logging artifacts can trigger similar heuristics. An analyst must review the evidence; no automatic sanction follows.

This public repository contains the generated synthetic report and a browser replay, but no private source, runnable input fixture or live API. Ask the owner for a supervised session to see an actual engine run and inspect the private code.

## Operator pilot acceptance plan

Before production use, agree on authorized fields, pseudonymization and retention. Run in **shadow mode** on appropriately anonymized event telemetry with independently reviewed case labels. Measure importer coverage and failures, alert volume per 1,000 players, analyst review time, confusion matrix by a pre-agreed unit and false-positive burden. Examine difficult legitimate-play examples and missing-data cases. Set thresholds with the integrity team. Do not infer performance from synthetic profiles or parser fixtures.

## Diligence questions

- Which event fields, timestamps, hand IDs and device pseudonyms can the operator provide?
- Which current hand-history formats must be supported, and how are unsupported lines handled?
- Can the buyer reproduce the private test run and Docker verification on its own host?
- What are the operator's requirements for access, audit, retention and deletion?
- What review-burden and accuracy targets would justify a larger pilot?
