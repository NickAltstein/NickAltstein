# Nick Altstein

**AI Infrastructure Engineer focused on agent security · New York, NY**

I build harnesses for AI agents: fail-closed tool authorization, signed receipts, adversarial tests.

[Try the live sandbox](https://sandbox.auditgpt.ai/?scenario=prod-drop-table&step=1) · [AuditGPT](https://auditgpt.ai) · [LinkedIn](https://www.linkedin.com/in/nickaltstein/) · [Email](mailto:nickaltstein@gmail.com)

## Try it in your browser

Open the [blocked-call demo](https://sandbox.auditgpt.ai/?scenario=prod-drop-table&step=1), inspect why the simulated database call was denied, then verify its receipt. Change one byte and run verification again.

## Featured projects

<p align="center">
  <a href="https://github.com/NickAltstein/receiptd">
    <img src="assets/receiptd-banner.png" alt="Receiptd" width="600" />
  </a>
</p>

| Project | What I built |
| --- | --- |
| [Receiptd](https://github.com/NickAltstein/receiptd) | A fail-closed Claude Code `PreToolUse` hook (`pip install receiptd`). Tool calls routed through the hook produce Ed25519-signed, SHA-256 hash-chained receipts with a Merkle checkpoint every 100 receipts. `receiptd verify` checks the record offline. In a [pre-committed evaluation](https://github.com/NickAltstein/receiptd/blob/main/docs/eval/v1.5-scored-results.md) with two local models, the gate prevented 14 of 16 attempted attacks for Llama 3.1 8B and 5 of 10 for Qwen 2.5 7B; every miss is published. |
| [AuditGPT](https://auditgpt.ai) | A CLI for testing agent workflows across five failure classes, with terminal, Markdown, or SARIF output. Closed source. |
| [INFINI](https://github.com/NickAltstein/infini) | An agent loop CLI that writes traces to `run.json` and stops after two consecutive rounds with no new progress. |
| [Attestum](https://github.com/NickAltstein/Attestum) | A pre-launch project for evaluating changes to industrial robot cells using existing controller logs, video, and intervention records. No customers or assessments delivered yet. |

## How I evaluate

- Thresholds and scoring rules are committed before a run, and results are not regraded afterwards.
- New test cases are held out and hash-pinned before the fix author can see them.
- Misses, errors, and unmet targets are published alongside the passes.

## Background

Independent since 2024. I built **Scrutexity**, NYC building compliance software that turns public records into tracked obligations and evidence packages. Before that, I ran an Amazon import business for nine years, working directly with factories, suppliers, and a customs broker.

I also built [PropStein](https://propstein.com), a quantitative sports model. Holdout evaluations are in the repository; the week-1 Brier skill is negative.

**Tools I use:** Python, TypeScript, React, Next.js, SQL, GitHub Actions, pytest, Playwright.
