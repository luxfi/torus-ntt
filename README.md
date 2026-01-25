# Torus NTT

High-performance Number Theoretic Transform (NTT) library for FHE operations.

## Overview

NTT is a critical primitive for efficient polynomial arithmetic in FHE schemes. This library provides optimized implementations with GPU acceleration support.

## Features

- **SIMD optimizations**: AVX2/AVX-512 vectorization
- **GPU support**: CUDA and Metal backends
- **Configurable parameters**: Multiple NTT sizes and moduli
- **Integration ready**: Works with luxfi/fhe and luxfi/lattice

## Installation

```bash
pip install torus-ntt
```

## Usage

```python
from torus.ntt import NTT

# Create NTT instance
ntt = NTT(n=1024, modulus=0x1fffffffffe00001)

# Forward and inverse transforms
coeffs = [1, 2, 3, 4] + [0] * 1020
ntt_coeffs = ntt.forward(coeffs)
recovered = ntt.inverse(ntt_coeffs)
```

## Links

- [luxfi/fhe](https://github.com/luxfi/fhe)
- [Lux Network](https://lux.network)
