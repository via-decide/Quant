You are working in repository via-decide/Quant on branch main.

MISSION
Implement an optimized signal pipeline (via-signal-generator) and ML inference engine (via-quant-ml). 1. Create src/core/alpha/ and src/core/alpha/ml/. 2. Implement SignalOrchestrator.ts to manage independent AlphaModel instances. 3. Create IndicatorEngine.ts with $O(1)$ incremental updates using circular buffers. 4. Implement OrderBookImbalance.ts for micro-structure feature extraction. 5. Build an InferenceWorker.ts using WebAssembly/ONNX to run predictive ML models on a dedicated thread. 6. Implement FeatureStore.ts to pass data to the ML worker instantly via SharedArrayBuffer.

CONSTRAINTS
Absolutely no $O(N)$ calculations on the hot path. ML inference must use WASM SIMD and avoid blocking the main trading thread.

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