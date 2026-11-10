# model-architectures

Last updated: 2026-11-10

Model definitions and weight compatibility that arbitrary trainers and inference
consumers can use independently.

**Status: planned.** This repository owns requirements, target interfaces and
source lineage. It has no implemented model, Python package or training engine.

## Independent consumer and contract

A consumer supplies a versioned architecture/configuration and initialization or
compatible weights. The intended library constructs the model and exposes
forward, generation and cache behavior with documented shapes, precision and
weight-format compatibility. A consumer need not install a pretraining trainer.

[Specification and acceptance](docs/specs/README.md) ·
[Model-family blueprint](docs/specs/blueprint.md) ·
[Source lineage](docs/sources/lineage.json)

Model-pretraining owns optimization, data iteration, training-state resume and
base-model export orchestration. Model-posttraining owns adaptation. Model-serving
owns runtime adapters and endpoint lifecycle. ML-foundations retains educational
classical ML work; a tiny trainer can consume this library as a reference example.

Architecture internals remain together: attention, normalization, position
encoding, MLP and model sizes are not separate repositories. Lab can assemble
compatible releases but is never required by this product.

MIT covers authored documentation. External weights, code and datasets retain
their terms. No GPU use, model execution, recovered implementation or scientific
result is established by this planned home.
