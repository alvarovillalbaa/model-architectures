# 9. Phase 5 — model architecture

Start with a dense decoder-only transformer. Do not start with MoE.

## Baseline architecture

Use a modern Llama-like architecture:

* decoder-only causal LM
* RMSNorm
* SwiGLU
* RoPE
* grouped-query attention for larger models
* no dropout or very low dropout
* tied or untied embeddings, but document the choice
* context length 2048 or 4096 for base pretraining
* long-context extension as a separate stage

## Suggested model ladder

| Name     | Params | Layers |    Hidden | Heads |   Seq len |
| -------- | -----: | -----: | --------: | ----: | --------: |
| lab-124m |  ~124M |     12 |       768 |    12 |      2048 |
| lab-350m |  ~350M |     24 |      1024 |    16 | 2048/4096 |
| lab-1.3b |  ~1.3B |     24 |      2048 | 16/32 |      4096 |
| lab-3b   |    ~3B |     32 | 2560/3072 |    32 |      4096 |
| lab-7b   |    ~7B |     32 |      4096 |    32 |      4096 |

Exact shapes should be chosen to fit your framework and GPU memory.

## Research architecture track

Only after the dense baseline works, test:

1. hybrid attention/RNN layers
2. sliding-window attention
3. sparse attention
4. MoE
5. modular expert post-training

Hybrid architectures are a serious research direction. Ai2’s Olmo Hybrid replaced many attention layers with Gated DeltaNet-style recurrent layers and reported large token-efficiency gains in controlled comparisons, so this is a credible place to explore improvements. ([allenai.org][13])
