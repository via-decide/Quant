Repair mode for repository via-decide/Quant.

TARGET
Validate and repair only the files touched by the previous implementation.

TASK
Implement an optimized signal pipeline (via-signal-generator) and ML inference engine (via-quant-ml). 1. Create src/core/alpha/ and src/core/alpha/ml/. 2. Implement SignalOrchestrator.ts to manage independent AlphaModel instances. 3. Create IndicatorEngine.ts with $O(1)$ incremental updates using circular buffers. 4. Implement OrderBookImbalance.ts for micro-structure feature extraction. 5. Build an InferenceWorker.ts using WebAssembly/ONNX to run predictive ML models on a dedicated thread. 6. Implement FeatureStore.ts to pass data to the ML worker instantly via SharedArrayBuffer.

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