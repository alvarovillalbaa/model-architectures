# 5. Phase 1 — learn by building the smallest full system

Before scaling, build a toy trainer yourself.

## Goal

Train a **20M–60M decoder-only transformer** from scratch on a tiny corpus and serve it.

## Build manually

Implement:

1. tokenizer loading
2. packed dataset loader
3. transformer block
4. RoPE
5. RMSNorm
6. SwiGLU MLP
7. causal attention
8. AdamW
9. cosine or warmup-stable-decay schedule
10. checkpoint save/load
11. eval loss
12. text generation
13. simple chat wrapper
14. vLLM/Transformers export path if possible

This teaches you the mechanics. Then stop writing your own trainer. Move to OLMo-core/TorchTitan.

## Deliverable

A blog post: **“Training a tiny LLM from scratch: every tensor, every bug, every metric.”**

This is not for performance. It is for credibility and personal understanding.
