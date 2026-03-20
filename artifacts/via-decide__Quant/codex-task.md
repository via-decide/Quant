You are working in repository via-decide/Quant on branch main.

MISSION
Implement an ultra-low-latency risk firewall called via-quant-risk to intercept and size all outbound orders. 1. Create src/core/risk-management/. 2. Implement RiskEngine.ts as the final gatekeeper for all strategy signals. 3. Create PositionSizer.ts to dynamically calculate optimal trade sizes based on portfolio equity and volatility. 4. Implement ExposureLimits.ts to enforce max gross/net exposure and single-asset concentration limits. 5. Build MarginTracker.ts to simulate exchange liquidation engines in real-time. 6. Implement a CircuitBreaker.ts to trigger a global "Cancel All" if anomalous latency or flash crashes occur.

CONSTRAINTS
The RiskEngine MUST execute all checks in under 5 microseconds. Absolutely no synchronous DB queries or GC allocations during the validation phase.

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