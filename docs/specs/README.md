# Model architecture contract

Last updated: 2026-11-10

Status: planned; all interfaces below are intended behavior.

- Configuration identifies the model family/version, layer dimensions, attention,
  normalization, positional encoding, vocabulary/tokenizer compatibility and
  supported context/cache behavior.
- Construction accepts explicit initialization and seeds or an exact permitted
  weight reference. It must not silently fetch weights.
- Forward and generation operations document inputs, outputs, masks, cache state,
  precision/device constraints and deterministic-mode limits.
- Weight import/export validates names, shapes, types, format and architecture
  compatibility; it does not restore optimizer or data-loader state.
- Consumers can supply external training loops, inference runtimes and probes.

## First implementation and acceptance

- [ ] Implement one tiny dense decoder model with a documented configuration.
- [ ] Verify shapes, causal masking, numerical behavior and cache equivalence.
- [ ] Prove seeded construction and a bounded CPU forward/generation example.
- [ ] Round-trip weights/config and load them from a separately installed consumer.
- [ ] Select optional backend dependencies explicitly before adding other families.

No training loss/optimizer service, serving endpoint, artifact storage engine or
mandatory Lab import belongs here. Backend conversion must preserve its observed
compatibility limits. The first implementation may choose one format; it must
not claim compatibility with every runtime.
