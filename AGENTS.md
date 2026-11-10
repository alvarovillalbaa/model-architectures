# Model architectures agent instructions

- Read README.md and docs/specs/README.md first.
- Own model configuration, math, initialization, forward/generation/cache and weight-format compatibility.
- Training orchestration, optimizer/resume state and data iteration belong to trainers.
- This repository is a planned product; no model engine or package exists yet.
- Keep architecture families coherent. Never create a repository per layer or parameter size.
- Preserve exact source fragments, hashes and extraction maps. Do not download models implicitly.
