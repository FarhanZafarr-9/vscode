# Intelligent Developer OS

Intelligent Developer OS is a final-year project built as a native fork of Code - OSS. It integrates AI model routing and edit review into the editor while supporting fully manual development. The project index powers repository navigation and analysis with AI turned off.

## Feature roadmap

The lists below describe the planned scope for each project phase.

### FYP-I feature checklist

Pick any unchecked item and note your claim in the issue or pull request. Prerequisites indicate what must be ready for integration. You can start against a stub or fixture while a dependency is being built.

- [ ] **F1 · Code - OSS foundation** — Pin the upstream revision and document a reproducible Windows development build. **Prerequisites** — None.
- [ ] **F2 · Project Index** — Scan workspace files, extract symbols and dependency edges through language adapters, and update the SQLite index as files change. **Prerequisites** — F1 for integration.
- [ ] **F3 · Provider catalog and credentials** — Build the shared provider interface, gateway client, model catalog, and secure credential storage. Verify access to at least three free-tier providers. **Prerequisites** — F1 for integration.
- [ ] **F4 · Provider onboarding** — Guide developers through saving a gateway credential and checking the connection. **Prerequisites** — F3's credential and connection-check interfaces.
- [ ] **F5 · Prompt Classifier and Model Router (M1)** — Classify request complexity, rank models by quality, quota, latency, and cost, and try fallbacks after failures or rate limits. **Prerequisites** — F2's index query interface and F3's provider and catalog interfaces.
- [ ] **F6 · Context Budget Indicator** — Show estimated context use against the selected model's window. **Prerequisites** — F3's model limits and F5's routing result with a context estimate.
- [ ] **F7 · Project Dashboard** — Show workspace structure and index status. **Prerequisites** — F2's file and index-status queries.
- [ ] **F8 · File Connectivity Graph** — Visualize indexed files and the import relationships between them. **Prerequisites** — F2's dependency graph query.
- [ ] **F9 · Git panel and commit grouping** — Review repository changes and group related changes into commits. **Prerequisites** — F1 for integration and a local Git repository with sample changes for validation.
- [ ] **F10 · Workflow Builder** — Configure and run recurring development tasks from the editor. **Prerequisites** — F1 for integration and a sample workspace task to exercise the workflow.

### FYP-II — Context, edit review, and automation

- **Context Chunker and Multi-Model Orchestrator (M2)** — Select relevant repository context, split it when it exceeds the model's context window, and combine results across calls.
- **Pre-Edit Hallucination Guard (M3)** — Check proposed edits for relevance and structural consistency before applying them. Hold doubtful edits for the developer to approve, revise, or reject.
- **Causal Summarizer and Reasoning Timeline (M4)** — Record proposed changes, the model's stated rationale, and what was applied, held, or rejected.
- **Code Health Suite** — Surface findings from static analysis with AI disabled.
- **Deployment automation** — Extend the Workflow Builder to run deployment sequences.

## Research

The project uses a benchmark of repository tasks to study two questions.

1. How does multi-model routing affect task success, latency, and quota use compared with a fixed model?
2. How does pre-edit verification affect the rate of incorrect or irrelevant edits reaching the source tree?

The evaluation compares a fixed-model baseline with routing enabled, verification enabled, and both enabled.

## Development

The fork follows the [repository coding and validation guidelines](.github/copilot-instructions.md). For the upstream build and debugging workflow, see the [Code - OSS contributor guide](https://github.com/microsoft/vscode/wiki/How-to-Contribute). The repository also includes a [development container](.devcontainer/README.md).

## Team

- Farhan Zafar, Muhammad Ali, and Abdul Rehman
- Project advisor Ms. Sana Fatima
- FAST National University of Computer and Emerging Sciences, Lahore

## Upstream and license

Intelligent Developer OS is based on [Code - OSS](https://github.com/microsoft/vscode). The upstream source is copyright Microsoft Corporation and is licensed under the [MIT License](LICENSE.txt).
