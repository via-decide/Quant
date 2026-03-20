You are working in repository via-decide/Quant on branch main.

MISSION
Synthesize the quantitative system into ARCHITECTURE.md and generate automated documentation. 1. Create docs/architecture/ and a Docusaurus/VitePress workspace. 2. Draft ARCHITECTURE.md mapping the data flow: FIX -> Core -> Signal -> Risk -> Execution -> FIX. 3. Detail the "Zero-GC / Lock-Free" philosophy and SharedArrayBuffer usage. 4. Document backtester deterministic event-loops and strict lookahead bias prevention. 5. Implement DocGenerator.ts to scrape JSDoc comments into the static HTML portal.

CONSTRAINTS
Clearly separate the latency-critical "Hot Path" from the "Cold Path". The docs must act as the absolute source of truth for risk-management standards.
Implement institutional FIX connectivity (via-quant-fix) and a derivatives pricer (via-quant-options). 1. Create src/core/connectivity/fix/ and src/core/derivatives/. 2. Implement FixSession.ts to manage raw TCP sockets, logon sequences, and heartbeats. 3. Create ZeroCopyParser.ts to parse \x01 delimited FIX byte streams directly into memory pools. 4. Implement BlackScholes.ts for vectorized European options pricing. 5. Build GreeksCalculator.ts (Delta, Gamma, Theta, Vega, Rho) and ImpliedVolatility.ts (Newton-Raphson). 6. Expose an interactive 3D WebGL Volatility Surface dashboard.

CONSTRAINTS
String manipulation is forbidden on the FIX hot path. Use polynomial approximations or lookup tables for Cumulative Normal Distribution functions in options pricing.
Implement a Smart Order Routing (SOR) pipeline called via-execution-router to slice large parent orders. 1. Create src/core/execution/. 2. Implement an ExecutionEngine.ts to manage Parent orders and spawn fractional Child orders. 3. Create SmartOrderRouter.ts to analyze consolidated L2 books and route to venues with the best price/liquidity. 4. Implement AlgoSniper.ts for VWAP/TWAP order slicing algorithms. 5. Build IcebergManager.ts to replenish visible limit order quantities from hidden parent sizes. 6. Implement a FillReconciler.ts to aggregate partial fills and calculate blended entry prices.

CONSTRAINTS
Do not block the signal-generation loop. Track child order states asynchronously via WebSocket User Data streams, not REST APIs.
Implement an optimized signal pipeline (via-signal-generator) and ML inference engine (via-quant-ml). 1. Create src/core/alpha/ and src/core/alpha/ml/. 2. Implement SignalOrchestrator.ts to manage independent AlphaModel instances. 3. Create IndicatorEngine.ts with $O(1)$ incremental updates using circular buffers. 4. Implement OrderBookImbalance.ts for micro-structure feature extraction. 5. Build an InferenceWorker.ts using WebAssembly/ONNX to run predictive ML models on a dedicated thread. 6. Implement FeatureStore.ts to pass data to the ML worker instantly via SharedArrayBuffer.

CONSTRAINTS
Absolutely no $O(N)$ calculations on the hot path. ML inference must use WASM SIMD and avoid blocking the main trading thread.
Implement an ultra-low-latency risk firewall called via-quant-risk to intercept and size all outbound orders. 1. Create src/core/risk-management/. 2. Implement RiskEngine.ts as the final gatekeeper for all strategy signals. 3. Create PositionSizer.ts to dynamically calculate optimal trade sizes based on portfolio equity and volatility. 4. Implement ExposureLimits.ts to enforce max gross/net exposure and single-asset concentration limits. 5. Build MarginTracker.ts to simulate exchange liquidation engines in real-time. 6. Implement a CircuitBreaker.ts to trigger a global "Cancel All" if anomalous latency or flash crashes occur.

CONSTRAINTS
The RiskEngine MUST execute all checks in under 5 microseconds. Absolutely no synchronous DB queries or GC allocations during the validation phase.
Implement a deterministic historical simulator called via-quant-backtester to evaluate trading strategies. 1. Create src/core/backtest/. 2. Implement HistoricalDataFeeder.ts to stream Parquet files directly into the RingBuffer. 3. Create an EventEngine.ts to sequentially process Market, Signal, Order, and Fill events deterministically. 4. Implement SimulatedExchange.ts to cross orders against historical L2 data, simulating latency and slippage. 5. Build AccountTracker.ts to maintain a running ledger of cash and margin. 6. Implement a MetricsEngine.ts to calculate Max Drawdown, Beta, and Sharpe Ratio.

CONSTRAINTS
Ensure absolute parity between the Backtesting Engine and the Live Trading Engine. Strictly forbid "lookahead bias" by tightly encapsulating the data feeder.
Implement a deterministic, zero-allocation market data ingestor and L2 Order Book called via-quant-core. 1. Create src/core/market-data/. 2. Implement OrderBook.ts using flat Float64Array buffers or WebAssembly/Rust for $O(\log n)$ insertions/deletions. 3. Create FeedHandler.ts to parse WebSocket feeds (JSON/binary) and update the book without GC pressure. 4. Implement a RingBuffer.ts (lock-free queue) to pass updates to worker threads, bypassing Node.js serialization. 5. Build OrderManager.ts to track local order states. 6. Implement a TickSnapshot.ts service to compress L2 state into a Time-Series DB (QuestDB/InfluxDB).

CONSTRAINTS
Strictly enforce zero-allocation on the hot path. Forbid new Object(), [], or JSON.parse() during the active trading loop to prevent garbage collection pauses and slippage.

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