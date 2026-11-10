# Model-family blueprint

Last updated: 2026-11-10

This is a planned projection of original Lab model-math requirements. Exact source
fragments and the previous pretraining projection are preserved under docs/sources.

The first family is a small dense causal decoder: RMSNorm, RoPE, SwiGLU and causal
attention, with explicitly chosen embedding tying, masks and context limits.
Larger variants may use grouped-query attention. Parameter sizes are configured
variants of one coherent library.

After a validated baseline, research may compare hybrid/recurrent, sliding-window,
sparse-attention and mixture-of-expert families. These are research directions,
not implemented engines or established improvement claims.

A tiny from-scratch training example may use these definitions; production trainers
may instead select external compatible architectures. Model-pretraining owns the
training loop and its choice of implementation, not the canonical model math here.
