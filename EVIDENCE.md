# GameGuard AI v0.5 — local verification, 26 September 2026

This record documents a **local run of the private source package**. It is not an independent operator evaluation or a production certification.

## Inputs and commands

- Source: `GameGuard_AI_v0.5_Private_Source.zip`, SHA-256 `4327e6ea9816a2cfc59704847194b32da891b0c8a0f9a53455e0451cad096446`.
- Runtime: Python 3.12.14, Linux.
- From the extracted `gameguard_ai/` directory:

```bash
python3 -m unittest discover -s tests -v
python3 demo/render_report.py
sha256sum demo/synthetic_report.json
```

## Observed results

- `Ran 29 tests in 0.514s` — `OK` (29/29).
- Generated [synthetic_report.json](synthetic_report.json), SHA-256 `6f3b9dfe6d8298a5a857a986552c07ddc3a2d217e5a21a05b737c653d59d039b`.
- Report: 360 decisions in two synthetic profiles. `human_demo`: 180 decisions, 180 hands, score 0, monitor, no evidence signals. `scripted_demo`: 180 decisions, 180 hands, score 45, review, with `low_latency_variation` (+25) and `repeated_spot_consistency` (+20). Device-link input unavailable in both profiles.
- [Interactive replay](https://inkh95.github.io/gameguard-ai-acquisition/) displays a **reduced projection** of this generated report. It runs in the browser with no backend and does not re-run the engine.

## Limits

The source package and tests remain private; an outside visitor cannot independently reproduce the result from this public repository. The synthetic data and labels do not measure detection quality, real-world false positives, or identification of AI/RTA use. The 15 public historical hand histories were used only for a limited parser check, not in the synthetic report. Docker build was not run in this verification. Request supervised source review and an operator-approved shadow-mode pilot for further validation.
