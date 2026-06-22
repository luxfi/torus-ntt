# Torus NTT

High-performance Number Theoretic Transform (NTT) library for FHE operations.

## Overview

NTT is a critical primitive for efficient polynomial arithmetic in FHE schemes. This library provides CPU-SIMD-optimized implementations.

## Features

- **SIMD optimizations**: AVX2/AVX-512 vectorization on x86-64 (via `pulp`); scalar fallback on other architectures
- **Configurable parameters**: Multiple NTT sizes and moduli
- **Integration ready**: Works with luxfi/fhe and luxfi/lattice

> **Compute backend: CPU only.** This crate has no GPU backend — there is no
> CUDA, Metal, or other accelerator code, and no GPU feature flags. The only
> hardware acceleration is x86-64 SIMD (AVX2/AVX-512). GPU-resident NTT in the
> Lux FHE stack lives on the Go side (`luxfi/fhe` `ntt_gpu.go`, dispatching to
> `luxfi/lattice`'s Metal/CUDA path), not in this crate.

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
