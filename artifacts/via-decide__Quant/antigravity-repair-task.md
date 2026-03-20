Repair mode for repository via-decide/Quant.

TARGET
Validate and repair only the files touched by the previous implementation.

TASK
Implement institutional FIX connectivity (via-quant-fix) and a derivatives pricer (via-quant-options). 1. Create src/core/connectivity/fix/ and src/core/derivatives/. 2. Implement FixSession.ts to manage raw TCP sockets, logon sequences, and heartbeats. 3. Create ZeroCopyParser.ts to parse \x01 delimited FIX byte streams directly into memory pools. 4. Implement BlackScholes.ts for vectorized European options pricing. 5. Build GreeksCalculator.ts (Delta, Gamma, Theta, Vega, Rho) and ImpliedVolatility.ts (Newton-Raphson). 6. Expose an interactive 3D WebGL Volatility Surface dashboard.

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