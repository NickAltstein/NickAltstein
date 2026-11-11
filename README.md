# Nick Altstein

**AI Infrastructure Engineer focused on agent security · New York, NY**

I build open-source tools that test agent workflows in CI, enforce policy on tool calls, and produce signed records that reviewers can verify offline.

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
| [Receiptd](https://github.com/NickAltstein/receiptd) | A fail-closed Claude Code `PreToolUse` hook. Tool calls routed through the hook produce Ed25519-signed, SHA-256 hash-chained receipts with a Merkle checkpoint every 100 receipts. `receiptd verify` checks the record offline. |
| [AuditGPT](https://auditgpt.ai) | An MIT-licensed CLI that tests agent workflows across five failure classes and reports findings in terminal, Markdown, or SARIF for CI. |
| [INFINI](https://github.com/NickAltstein/infini) | An agent loop CLI that writes traces to `run.json` and stops after two consecutive rounds with no new progress. |
| [Attestum](https://github.com/NickAltstein/Attestum) | A pre-launch project for evaluating changes to industrial robot cells using existing controller logs, video, and intervention records. No customers or assessments delivered yet. |

## Background

Independent since 2024. I built **Scrutexity**, NYC building compliance software that turns public records into tracked obligations and evidence packages. Before that, I ran an Amazon import business for nine years, working directly with factories, suppliers, and a customs broker.

I also built [PropStein](https://propstein.com), a quantitative sports modeling project with published holdout results and a reproducible verification workflow.

**Tools I use:** Python, TypeScript, React, Next.js, SQL, GitHub Actions, pytest, Playwright.
