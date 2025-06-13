# GC Crisis Lab Trading

A comprehensive GC stress testing simulation for trading systems. This project simulates high-frequency trading workloads to analyze garbage collection performance under various scenarios.

## Project Structure

```
gc-crisis-lab-trading/
├── engine/                         # Core trading engine
│   ├── FuturesEngine.java         # In-memory matching + position engine
│   ├── Position.java              # Position model simulating memory pressure
│   ├── Order.java                 # Simplified order model
│   ├── OrderBook.java            # Optional: symbol-level order book
│   └── ExecutionReport.java      # Simulated trade fill reports
│
├── stress/                        # Load generation
│   ├── OrderTrafficDriver.java   # Multi-threaded traffic simulation (Binance scale)
│   ├── OrderCancelStorm.java     # GC Crisis Scenario #2
│   └── PnLFlushSimulator.java    # GC Crisis Scenario #3
│
├── metrics/                       # GC monitoring tools
│   ├── GCPauseMonitor.java       # GC pause time tracking (jstat, logs)
│   ├── JFRMetricsReader.java     # Parse and display key JFR metrics
│   ├── GCLogParser.java          # Parse and summarize GC logs
│   └── ThroughputMeter.java      # Real-time OPS/RPS tracker
│
├── tuning/                        # GC config tuning
│   ├── GCFlagProfiles.md         # Cheatsheet of tuning flags per GC type
│   ├── gc-g1.conf                # Flags for G1
│   ├── gc-zgc.conf               # Flags for ZGC
│   ├── benchmark.sh              # Auto benchmark runner
│   └── analyze.sh                # Compare GC logs + throughput
│
├── tooling/                       # Profiling tools & visualizations
│   ├── profiler/
│   │   └── async-profiler.sh     # Flamegraph runner
│   └── visualizer/
│       └── gc-log-analyzer.html  # Custom GC log visualizer
│
├── scripts/
│   ├── run-g1.sh                 # G1 runner with default flags
│   ├── run-zgc.sh                # ZGC runner
│   └── stress-loop.sh           # Long-duration stress test
│
├── results/                       # Output & logs
│   ├── gc-g1.log
│   ├── gc-zgc.log
│   ├── profile-g1.svg
│   └── metrics-report.md
│
├── README.md
├── pom.xml
└── .gitignore
```

## Getting Started

TODO: Add build and run instructions

## GC Crisis Scenarios

TODO: Document the specific GC crisis scenarios to be tested

## Benchmarking

TODO: Add benchmarking methodology and results analysis