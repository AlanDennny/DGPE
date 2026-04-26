# C Simulation Benchmark Results

## Test Configuration
- **Tool**: Vitis HLS 2025.2 (C Simulation)
- **Target**: XC7Z020CLG400-1
- **Data size (N)**: 1000
- **Top-K (K)**: 10
- **Hardware frequency**: 171.94 MHz (post-implementation)
- **ARM baseline**: Cortex-A9 @ 667 MHz (estimated from host CPU timing)

## Results

### Uniform Distribution
- Evolution Rounds: 129
- DGPE Hardware Latency: 129.47 µs
- ARM Estimated Latency: 930.23 µs
- Speedup: **7.18x**
- Accuracy: PASS

### Zipf Distribution
- Evolution Rounds: 129
- DGPE Hardware Latency: 129.47 µs
- ARM Estimated Latency: 795.02 µs
- Speedup: **6.14x**
- Accuracy: PASS

### Constant Distribution
- Evolution Rounds: 129
- DGPE Hardware Latency: 129.47 µs
- ARM Estimated Latency: 528.26 µs
- Speedup: **4.08x**
- Accuracy: PASS

## Notes
- All three distributions passed functional verification.
- The worst-case latency is deterministic at 129.47 µs regardless of data distribution.
- Stream depth maxed at 1000 elements, matching the input size.
