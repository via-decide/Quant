Repair mode for repository via-decide/Quant.

TARGET
Validate and repair only the files touched by the previous implementation.

TASK
Synthesize the quantitative system into ARCHITECTURE.md and generate automated documentation. 1. Create docs/architecture/ and a Docusaurus/VitePress workspace. 2. Draft ARCHITECTURE.md mapping the data flow: FIX -> Core -> Signal -> Risk -> Execution -> FIX. 3. Detail the "Zero-GC / Lock-Free" philosophy and SharedArrayBuffer usage. 4. Document backtester deterministic event-loops and strict lookahead bias prevention. 5. Implement DocGenerator.ts to scrape JSDoc comments into the static HTML portal.
Implement institutional FIX connectivity (via-quant-fix) and a derivatives pricer (via-quant-options). 1. Create src/core/connectivity/fix/ and src/core/derivatives/. 2. Implement FixSession.ts to manage raw TCP sockets, logon sequences, and heartbeats. 3. Create ZeroCopyParser.ts to parse \x01 delimited FIX byte streams directly into memory pools. 4. Implement BlackScholes.ts for vectorized European options pricing. 5. Build GreeksCalculator.ts (Delta, Gamma, Theta, Vega, Rho) and ImpliedVolatility.ts (Newton-Raphson). 6. Expose an interactive 3D WebGL Volatility Surface dashboard.
Implement a Smart Order Routing (SOR) pipeline called via-execution-router to slice large parent orders. 1. Create src/core/execution/. 2. Implement an ExecutionEngine.ts to manage Parent orders and spawn fractional Child orders. 3. Create SmartOrderRouter.ts to analyze consolidated L2 books and route to venues with the best price/liquidity. 4. Implement AlgoSniper.ts for VWAP/TWAP order slicing algorithms. 5. Build IcebergManager.ts to replenish visible limit order quantities from hidden parent sizes. 6. Implement a FillReconciler.ts to aggregate partial fills and calculate blended entry prices.
Implement an ultra-low-latency risk firewall called via-quant-risk to intercept and size all outbound orders. 1. Create src/core/risk-management/. 2. Implement RiskEngine.ts as the final gatekeeper for all strategy signals. 3. Create PositionSizer.ts to dynamically calculate optimal trade sizes based on portfolio equity and volatility. 4. Implement ExposureLimits.ts to enforce max gross/net exposure and single-asset concentration limits. 5. Build MarginTracker.ts to simulate exchange liquidation engines in real-time. 6. Implement a CircuitBreaker.ts to trigger a global "Cancel All" if anomalous latency or flash crashes occur.
Implement a deterministic historical simulator called via-quant-backtester to evaluate trading strategies. 1. Create src/core/backtest/. 2. Implement HistoricalDataFeeder.ts to stream Parquet files directly into the RingBuffer. 3. Create an EventEngine.ts to sequentially process Market, Signal, Order, and Fill events deterministically. 4. Implement SimulatedExchange.ts to cross orders against historical L2 data, simulating latency and slippage. 5. Build AccountTracker.ts to maintain a running ledger of cash and margin. 6. Implement a MetricsEngine.ts to calculate Max Drawdown, Beta, and Sharpe Ratio.
Implement a deterministic, zero-allocation market data ingestor and L2 Order Book called via-quant-core. 1. Create src/core/market-data/. 2. Implement OrderBook.ts using flat Float64Array buffers or WebAssembly/Rust for $O(\log n)$ insertions/deletions. 3. Create FeedHandler.ts to parse WebSocket feeds (JSON/binary) and update the book without GC pressure. 4. Implement a RingBuffer.ts (lock-free queue) to pass updates to worker threads, bypassing Node.js serialization. 5. Build OrderManager.ts to track local order states. 6. Implement a TickSnapshot.ts service to compress L2 state into a Time-Series DB (QuestDB/InfluxDB).

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