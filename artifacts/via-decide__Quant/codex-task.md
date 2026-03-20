You are working in repository via-decide/Quant on branch main.

MISSION
Synthesize the quantitative system into ARCHITECTURE.md and generate automated documentation. 1. Create docs/architecture/ and a Docusaurus/VitePress workspace. 2. Draft ARCHITECTURE.md mapping the data flow: FIX -> Core -> Signal -> Risk -> Execution -> FIX. 3. Detail the "Zero-GC / Lock-Free" philosophy and SharedArrayBuffer usage. 4. Document backtester deterministic event-loops and strict lookahead bias prevention. 5. Implement DocGenerator.ts to scrape JSDoc comments into the static HTML portal.

CONSTRAINTS
Clearly separate the latency-critical "Hot Path" from the "Cold Path". The docs must act as the absolute source of truth for risk-management standards.

PROCESS (MANDATORY)
1. Read README.md and AGENTS.md before editing.
2. Audit architecture before coding. Summarize current behavior.
3. Preserve unrelated working code. Prefer additive modular changes.
4. Implement the smallest safe change set for the stated goal.
5. Run validation commands and fix discovered issues.
6. Self-review for regressions, missing env wiring, and docs drift.
7. Return complete final file contents for every modified or created file.

REPO AUDIT CONTEXT
- Description: 
- Primary language: HTML
- README snippet:
not found

- AGENTS snippet:
not found


SOP: PRE-MODIFICATION PROTOCOL (MANDATORY)
1. Adherence to Instructions: No deviations without explicit user approval.
2. Mandatory Clarification: Immediately ask if instructions are ambiguous or incomplete.
3. Proposal First: Always propose optimizations or fixes before implementing them.
4. Scope Discipline: Do not add unrequested features or modify unrelated code.
5. Vulnerability Check: Immediately flag and explain security risks.

OUTPUT REQUIREMENTS
- Include: implementation summary, checks run, risks, rollback notes.
- Generate branch + PR package.
- Keep prompts deterministic and preservation-first.