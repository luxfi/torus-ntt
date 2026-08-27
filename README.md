# torus-ntt

Retired. This was a Rust number-theoretic transform. The implementations this
project uses are:

- **Go** — `luxfi/fhe` (`ntt_simd.go`, `ntt_gpu.go`), which the F-Chain daemon
  links and whose tests cover round-trip, SIMD and batch equality.
- **C++** — `luxcpp/crypto`, `luxcpp/fhe`.
- **GPU** — `lux-private/gpu-kernels`.

No manifest in the estate named this crate when it was removed.
