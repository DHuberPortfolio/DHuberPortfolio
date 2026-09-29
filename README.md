### Devin Huber

I build AI systems, and measure how often they're wrong.

I started building AI agents about a year ago in n8n and Zapier, for my job and as spec builds for companies I wanted to work for. The more of them I shipped, the more one question mattered: were they right? Their own scorecards weren't answering it honestly. One reported a 100% catch rate while 30% of what it let through still needed a person. So I built a tool that answers it, and I'm moving more of my work from workflow builders into tested code.

Everything here is scored against answers written before it ran, and reported even when the result came back negative.

**[devinhuber.com](https://devinhuber.com)** · [LinkedIn](https://www.linkedin.com/in/devinhuber/) · [Résumé](https://devinhuber.com/resume/)

---

#### [workflow-eval-harness](https://github.com/DHuberPortfolio/workflow-eval-harness)

A zero-dependency Node.js CLI that grades any AI workflow's output against a labeled answer key. The headline metric is the **silent error rate**: of everything the workflow let through with no human in front of it, the share that needed one. Every rate carries a 95% range, because "0 errors in 7" is still consistent with a true rate of 35%.

- A compliance reviewer's own scorecard reported a **100% catch rate**. The harness measured **30%** of the documents it let through needing a person. One prompt change took that to **6.7%** in four runs out of four — five routes fixed, none broken.
- It reproduces a news-metadata agent's scorecard figure for figure, then reports what three fresh runs are worth.
- 170+ tests, run in CI on Linux and Windows across three Node versions, checked for teeth by breaking the code on purpose.

Built with Claude Code. [Full write-up and results →](https://devinhuber.com/eval-harness/)

#### [AIBuildsSeptemberShowcase](https://github.com/DHuberPortfolio/AIBuildsSeptemberShowcase)

Sanitized n8n exports of six workflows — client names, credentials, webhook IDs and internal URLs removed — each with a README covering what it does, how it is wired, and what it does when it is wrong. Includes a replay of the metadata agent's deterministic layers that matches a recorded production run on all 56 figures.

#### Now

- Growing each answer key toward ~500 labeled items, so a single miss stops swinging the error rate.
- Moving more workflows out of n8n and Zapier into code, with tests from the first commit.

---

The write-ups, including [an analysis where none of fifteen hypotheses survived](https://devinhuber.com/projects/summary-quality/), are at **[devinhuber.com](https://devinhuber.com)**.
