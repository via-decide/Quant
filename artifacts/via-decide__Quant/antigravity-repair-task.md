Repair mode for repository via-decide/Quant.

TARGET
Validate and repair only the files touched by the previous implementation.

TASK
Implement a Smart Order Routing (SOR) pipeline called via-execution-router to slice large parent orders. 1. Create src/core/execution/. 2. Implement an ExecutionEngine.ts to manage Parent orders and spawn fractional Child orders. 3. Create SmartOrderRouter.ts to analyze consolidated L2 books and route to venues with the best price/liquidity. 4. Implement AlgoSniper.ts for VWAP/TWAP order slicing algorithms. 5. Build IcebergManager.ts to replenish visible limit order quantities from hidden parent sizes. 6. Implement a FillReconciler.ts to aggregate partial fills and calculate blended entry prices.

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