### Devin Huber · AI automation engineer

I build AI automations that run on their own, and prove they work.
Five are in use at my employer today. My finance degree shows up in my newest build: a statement spreader for credit analysts, measured against SEC filings.

**[devinhuber.com](https://devinhuber.com)** · [Résumé](https://devinhuber.com/resume/) · [LinkedIn](https://www.linkedin.com/in/devinhuber/) · Columbus, OH · open to AI automation & AI engineering roles

<table>
<tr>
<td width="25%"><h2>5</h2>AI agents in use at my employer</td>
<td width="25%"><h2>98%</h2>of wrong values caught before they went out, on 87 sealed SEC filings</td>
<td width="25%"><h2>3×</h2>fewer wrong tags after my fix, 500-article stress test</td>
<td width="25%"><h2>0 of 33</h2>trick questions fooled my archive AI, one test run (likely 0–10.4%)</td>
</tr>
</table>

#### What's real and running

| Status | Builds |
|:--|:--|
| In use at my employer | Executive email assistant, Monday operations brief, guest application agent, newsletter agent, podcast archive assistant |
| Tested prototype | Finance operations platform (statement-spreader, below) |
| Open source, tested in CI | The evaluation harness and the four free tools below |

#### Code

- [**statement-spreader**](https://github.com/DHuberPortfolio/statement-spreader) does the keying and ticking finance teams do by hand. Statements in (an SEC 10-K, a PDF, an Excel workbook), a standard spread out, every number traced to the cell it was printed in and checked by accounting identities. A value goes out without an analyst only when two independent checks agree; everything else waits for a person, and approval is always a person's. On [87 sealed SEC filings](https://github.com/DHuberPortfolio/statement-spreader/blob/36049de/DECISIONS.md#L1191), opened only for a final test, it caught 663 of 677 wrong values before they went out (98%; likely 96.6–98.8%), and 0.9% of the values it accepted alone were wrong (14 of 1,572; likely 0.5–1.5%). About 80% of values still go to a person. The same platform reconciles bank lines to the ledger, matches invoices to purchase orders, gates vendor data before it loads, and scans workbooks for broken formulas, each measured on synthetic sets. No language model decides anything; it runs on one machine at $0. Python, 1,499 tests in CI.
- [**workflow-eval-harness**](https://github.com/DHuberPortfolio/workflow-eval-harness) grades any AI workflow against an answer key. Its headline metric is the silent error rate: what went out unchecked that needed a person. Node.js, zero dependencies, 996 tests in CI on Linux and Windows across three Node versions. It also scored the spreader's invoice and reconciliation output independently.
- [**n8n-ai-agent-workflows**](https://github.com/DHuberPortfolio/n8n-ai-agent-workflows) holds sanitized n8n agent workflows, a README each, and a replay that matches a recorded run on all 56 figures. One fix there cut wrong tags threefold on a 500-article stress test (27% to 8.6%, worst run; likely 5.5–13.1%).
- [**workout-ledger**](https://github.com/DHuberPortfolio/workout-ledger) is my own one-file fitness dashboard. [Try it](https://dhuberportfolio.github.io/workout-ledger/).

#### Free tools · try them in your browser

| Tool | What it answers |
|:--|:--|
| [**Error-rate calculator**](https://dhuberportfolio.github.io/error-rate-calculator/) | How wrong is your AI, really? Audited against statsmodels on 65,808 inputs. |
| [**Workflow cost calculator**](https://dhuberportfolio.github.io/workflow-cost-calculator/) | What your AI workflow really costs: the model, the reviewers and the misses. |
| [**Ready-to-ship checklist**](https://dhuberportfolio.github.io/ready-to-ship/) | Twelve questions before an AI runs on its own. |
| [**n8n export scrubber**](https://dhuberportfolio.github.io/n8n-export-scrubber/) | Share the workflow, not your keys. Nothing leaves your browser. |

Built with Claude Code, the Anthropic API, n8n, Zapier, Python, Node.js, MCP and GitHub Actions. My production work is private to my employer; [devinhuber.com](https://devinhuber.com) has a write-up of every build.
