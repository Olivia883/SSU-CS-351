# CS-351 Project 2:

## Overview

1. **Mean computation (`mean.cpp` → `threaded.cpp`)**  
2. **Volume computation (`sdf.cpp`)** using a signed distance function (Monte Carlo integration)

---

## Build Instructions

From the `Project-2` directory:

```bash
make mean.out
make threaded.out
make sdf.out

Volume Estimation (sdf.out)
Threads  Estimated Volume Fraction  Time (s)  Speedup
1        0                         0.00      1.0
2        2e-06                     0.00      1.0
4        4e-06                     0.00      1.0
8        3.5e-05                    0.00      1.0

Observations:
Maximum speedup achieved: 1.0
Speedup curve converges due to serial overhead: Not observable
Linear scaling only up to available cores: Not observable
Estimated parallel fraction p (Amdahl’s Law): 100% (theoretical)

