Repair mode for repository via-decide/Quant.

TARGET
Validate and repair only the files touched by the previous implementation.

TASK
Implement a deterministic historical simulator called via-quant-backtester to evaluate trading strategies. 1. Create src/core/backtest/. 2. Implement HistoricalDataFeeder.ts to stream Parquet files directly into the RingBuffer. 3. Create an EventEngine.ts to sequentially process Market, Signal, Order, and Fill events deterministically. 4. Implement SimulatedExchange.ts to cross orders against historical L2 data, simulating latency and slippage. 5. Build AccountTracker.ts to maintain a running ledger of cash and margin. 6. Implement a MetricsEngine.ts to calculate Max Drawdown, Beta, and Sharpe Ratio.

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