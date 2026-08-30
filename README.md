# Hybrid Classical–Quantum Neural Network on AFIR-10

## Overview

This repository presents an experimental exploration of Quantum Neural Networks (QNNs) applied to the AFIR-10 dataset. The project is intentionally research-oriented, focusing on investigating the feasibility, limitations, and behavior of hybrid classical–quantum learning systems rather than achieving production-level performance.

Ideas are implemented, tested, observed, and sometimes abandoned. Broken components and unstable training behavior are documented as part of the learning process.

This project aims to examine fundamental questions in quantum machine learning, including:

- How classical features can be encoded into quantum states
- Whether entanglement and quantum correlations meaningfully enhance representation learning
- The practical challenges of training parameterized quantum circuits
- The effectiveness of hybrid classical–quantum pipelines
- The role of quantum-inspired techniques (e.g., surrogate gradients) when direct gradients are unavailable or unreliable


## Current Progress

### Implemented Components

- Hybrid classical–quantum neural network architecture
- Basic QNN forward pass using parameterized quantum circuits
- AFIR-10 dataset loading and preprocessing
- Integration with PyTorch training loops
- Classical CNN baseline for performance comparison
- Initial experiments involving:
  - Dimensionality reduction prior to quantum encoding
  - Measurement-based quantum outputs
  - Surrogate-gradient-based optimization

### Observations & Experimental Findings

- QNN training frequently plateaus early, even when the CNN baseline continues improving
- Gradient flow through quantum layers is often weak or noisy
- Training stability is highly sensitive to:
  - Encoding strategy
  - Circuit depth
  - Number of qubits
  - Measurement aggregation method
- In most configurations, classical preprocessing dominates performance

## Known Limitations

- Certain quantum operations or measurement pipelines may fail depending on backend versions
- End-to-end training is not consistently stable
- Current QNN performance does not surpass classical baselines
- Results should not be interpreted as evidence of quantum advantage

## Future Work

Planned and proposed directions include:

- Stabilizing the quantum training pipeline
- Exploring alternative encoding schemes (angle, amplitude, hybrid)
- Studying barren plateaus and gradient suppression
- Visualization of quantum measurement distributions
- Systematic benchmarking against classical models
- Ablation studies isolating quantum vs. classical contributions

## Environment and Compatibility Notes

Development of this project encountered several compatibility issues between quantum machine learning libraries and modern Python / deep learning environments. These issues currently prevent a stable end-to-end QNN training pipeline.

Observed problems include:

- TensorFlow Quantum incompatibilities with newer Keras / TensorFlow versions
- PennyLane import failures caused by mismatches with recent JAX releases
- Version conflicts between quantum libraries and Python 3.12
- Backend-dependent failures when constructing parameterized quantum circuits


### Planned Resolution

Once compatibility issues are resolved, the following steps are planned:

- Reintroduce a fully functional quantum circuit backend
- Replace surrogate layers with true parameterized quantum circuits
- Validate gradient flow through quantum layers
- Benchmark quantum and classical models under identical conditions
- Document the differences between surrogate and hardware-backed implementations

This section is intentionally maintained to document the tooling limitations currently present in quantum machine learning ecosystems and to enable future continuation of the project once stable environments become available.
