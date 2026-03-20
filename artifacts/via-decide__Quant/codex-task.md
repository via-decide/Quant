You are working in repository via-decide/Quant on branch main.

MISSION
Implement institutional FIX connectivity (via-quant-fix) and a derivatives pricer (via-quant-options). 1. Create src/core/connectivity/fix/ and src/core/derivatives/. 2. Implement FixSession.ts to manage raw TCP sockets, logon sequences, and heartbeats. 3. Create ZeroCopyParser.ts to parse \x01 delimited FIX byte streams directly into memory pools. 4. Implement BlackScholes.ts for vectorized European options pricing. 5. Build GreeksCalculator.ts (Delta, Gamma, Theta, Vega, Rho) and ImpliedVolatility.ts (Newton-Raphson). 6. Expose an interactive 3D WebGL Volatility Surface dashboard.

CONSTRAINTS
String manipulation is forbidden on the FIX hot path. Use polynomial approximations or lookup tables for Cumulative Normal Distribution functions in options pricing.

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