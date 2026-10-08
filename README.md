# AI Strategy Playbook

A source-grounded, guided workflow for moving from strategic intent and candidate AI opportunities to a defensible AI strategy report.

## Start here
1. Load all `core/`, `stages/` and `templates/` Markdown files as sources in a dedicated NotebookLM notebook.
2. Start a chat with the prompt in `core/01-notebooklm-operating-instructions.md` (copy the **Start prompt**). NotebookLM may not reliably treat an uploaded instruction source as system instructions, so paste the prompt into the conversation.
3. Use one question at a time, capture decisions and evidence, and run a checkpoint at the end of each stage.
4. Save the checkpoint externally as Markdown. To resume, supply your saved checkpoint and ask to resume the stage stated in it.
5. When ready, request the report per `templates/strategy-report-template.md`.

## Key distinction
Strategy-level decisions govern a portfolio; the opportunity tear-down evaluates individual initiatives. Do not infer an organisation-wide strategy from one use case.

## Source alignment
- `AI Strategy Template 3.docx`: seven sections: vision and alignment; operating model; approach to technology; governance and risk; workforce; roadmap and use-case priorities; delivering and monitoring; plus peer reflection.
- `AI and Automation Opportunity Tear Down.pdf`: opportunity framing, problem clarity, type of AI, value/outcomes, people/work, readiness, ethical and sustainability lenses.
- The tear-down source visibly jumps from section 4 to section 6: this playbook does not invent a missing source section. Our own workflow headings are original organisational structure.

All prompts, statuses, gates, scoring and checkpoint syntax are **playbook design proposals**, not rules stated in the supplied course worksheets. Validate real-world legal/regulatory obligations separately.

## Directory
`core/`: operating rules, stages, checkpoints, decisions and quality controls.
`stages/`: guided questions and exit criteria.
`templates/`: structured Markdown records and reports.
`examples/`: starter interaction.
