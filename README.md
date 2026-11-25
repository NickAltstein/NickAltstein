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
| [Receiptd](https://github.com/NickAltstein/receiptd) | A fail-closed Claude Code `PreToolUse` hook (`pip install receiptd`). Tool calls routed through the hook produce Ed25519-signed, SHA-256 hash-chained receipts with a Merkle checkpoint every 100 receipts. `receiptd verify` checks the record offline. [v1.5 scored results](https://github.com/NickAltstein/receiptd/blob/main/docs/eval/v1.5-scored-results.md): 50 cases × 2 models, Llama 14/16, qwen 5/10, no pooled rate; every miss is published. |
| [AuditGPT](https://github.com/NickAltstein/auditgpt) | Adversarial test battery across 5 failure classes, npm, MIT. Public source on GitHub; site at [auditgpt.ai](https://auditgpt.ai). |
| [INFINI](https://github.com/NickAltstein/infini) | An agent loop CLI that writes traces to `run.json` and stops after two consecutive rounds with no new progress. |

## How I evaluate

- Thresholds and scoring rules are committed before a run, and results are not regraded afterwards.
- New test cases are held out and hash-pinned before the fix author can see them.
- Misses, errors, and unmet targets are published alongside the passes.

## Background

Independent since 2024. I built **Scrutexity**, NYC building compliance software that turns public records into tracked obligations and evidence packages. Before that, I ran an Amazon import business for nine years, working directly with factories, suppliers, and a customs broker.

**Tools I use:** Python, TypeScript, React, Next.js, SQL, GitHub Actions, pytest, Playwright.
