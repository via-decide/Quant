Repair mode for repository via-decide/Quant.

TARGET
Validate and repair only the files touched by the previous implementation.

TASK
Implement an ultra-low-latency risk firewall called via-quant-risk to intercept and size all outbound orders. 1. Create src/core/risk-management/. 2. Implement RiskEngine.ts as the final gatekeeper for all strategy signals. 3. Create PositionSizer.ts to dynamically calculate optimal trade sizes based on portfolio equity and volatility. 4. Implement ExposureLimits.ts to enforce max gross/net exposure and single-asset concentration limits. 5. Build MarginTracker.ts to simulate exchange liquidation engines in real-time. 6. Implement a CircuitBreaker.ts to trigger a global "Cancel All" if anomalous latency or flash crashes occur.

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