Repair mode for repository via-decide/Quant.

TARGET
Validate and repair only the files touched by the previous implementation.

TASK
Synthesize the quantitative system into ARCHITECTURE.md and generate automated documentation. 1. Create docs/architecture/ and a Docusaurus/VitePress workspace. 2. Draft ARCHITECTURE.md mapping the data flow: FIX -> Core -> Signal -> Risk -> Execution -> FIX. 3. Detail the "Zero-GC / Lock-Free" philosophy and SharedArrayBuffer usage. 4. Document backtester deterministic event-loops and strict lookahead bias prevention. 5. Implement DocGenerator.ts to scrape JSDoc comments into the static HTML portal.

RULES
1. Audit touched files first and identify regressions.
2. Preserve architecture and naming conventions.
3. Make minimal repairs only; do not expand scope.
4. Re-run checks and provide concise root-cause notes.
5. Return complete contents for changed files only.

SOP: REPAIR PROTOCOL (MANDATORY)
1. Strict Fix Only: Do not use repair mode to expand scope or add features.
2. Regression Check: Audit why previous attempt failed before proposing a fix.
3. Minimal Footprint: Only return contents for the actual repaired files.

REPO CONTEXT
- README snippet:
not found
- AGENTS snippet:
not found
- package.json snippet:
not found