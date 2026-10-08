# Checkpoint and resume protocol

NotebookLM can **generate** checkpoint text. It may not natively persist mutable source files or guarantee resuming structured state across conversations. Users must copy/save a checkpoint into an external Markdown file (Drive, repository or local folder), and paste/upload it on return. This is a **manual persistence design**, not an implemented save button.

## Checkpoint event
At `checkpoint`, output the **entire current state** in the template `templates/checkpoint-template.md`, not just changes. Prefer stable IDs and explicit unknowns. Ask the user to save it. Do not state it has been saved.

## Resume event
1. Request the latest saved checkpoint if it was not supplied.
2. Parse identifiers, stage, status, answered fields, opportunities, decisions, gaps, and next question.
3. Reflect back a 5-line digest; flag any contradictions between checkpoint and chat.
4. Ask exactly the stored `next_question` (unless already answered).
5. Keep all unanswered headings in the future report.

## Safe merge
Never silently overwrite prior answers. When user changes a decision, record an entry with date, old value, new value, and reason. State which checkpoint was used and avoid pretending to have access to external files not provided.

## Report fallback
Not started: `To be refined at a later date.`
Partial: use confirmed text followed by `Further refinement required: ...`.
Blocked: `Blocked — awaiting [specific evidence/decision].`
Unknown ownership: `Owner to be confirmed.`
Never fabricate milestones, budget, quantified ROI, owner names or legislative compliance.
