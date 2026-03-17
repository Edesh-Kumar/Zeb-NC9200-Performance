# Laptop Cooling Pad Analysis — Cinebench Benchmark

Does a cooling pad actually help? I ran Cinebench multi-core with and without a cooling pad on my laptop and logged hardware telemetry with HWiNFO64 to find out.

**[→ View the interactive dashboard](https://yourusername.github.io/cooling-pad-analysis)**

---

## Hardware
- **CPU:** Intel Core i7-13650HX
- **Benchmark:** Cinebench R24 Multi-Core
- **Logging:** HWiNFO64, ~2s sample rate

## Key Findings

| Metric | Without Pad | With Pad | Δ |
|---|---|---|---|
| CPU Effective Clocks (avg) | 3,068 MHz | 3,283 MHz | **+7.0%** |
| CPU Package Power (avg) | 65.4 W | 74.9 W | **+14.5%** |
| CPU Package Power (max) | 120.8 W | 135.4 W | +12.1% |
| CPU Core Temp (avg) | 75.4 °C | 77.2 °C | +2.5% |
| CPU Core Temp (max) | 89 °C | 89 °C | same |
| GPU Temp (avg) | 54.8 °C | 53.8 °C | −1.8% |

## The Counterintuitive Result

The cooling pad didn't lower CPU temperatures — it raised them slightly. This is expected: better airflow removed the thermal bottleneck, allowing the CPU to sustain higher clock speeds and draw more power. It runs hotter because it's working harder, not because cooling got worse.

The peak temperature was identical (89°C) in both runs, confirming the pad doesn't change the thermal ceiling — it just delays hitting it, resulting in more sustained performance throughout the benchmark.

## Files

| File | Description |
|---|---|
| `index.html` | Interactive dashboard (Chart.js, single file, no dependencies) |
| `without_cooling_pad.CSV` | Raw HWiNFO64 log — no pad |
| `with_cooling_pad.CSV` | Raw HWiNFO64 log — with pad |
