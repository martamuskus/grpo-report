# Optimizing Chain-of-Thought Length in Small Language Models via Reinforcement Learning

**Marta Muskus, Grzegorz Dolanowski** · University of Warsaw

[Full report (PDF)](optimal_cot.pdf)

We study how reasoning length affects accuracy in small language models (Qwen2/2.5, 0.5B and 1.5B) on the MATH benchmark, and then use reinforcement learning to move them toward more efficient reasoning.

- **Optimal CoT length.** Using beam search with length penalties and within-problem sampling, we confirm an inverted-U relationship between chain-of-thought length and accuracy. The optimal length grows with problem difficulty, and the finding extends Wu et al. (2025) down to 0.5B models.
- **Length-regularized GRPO.** We fine-tune Qwen2.5-0.5B (LoRA) with GRPO and a correctness-gated length reward, `R = R_correct · (1 − λ · CoT_length)`.
- **Results.** Pooled MATH accuracy rises from 29.0% to 38.2%, and optimal reasoning length drops from 17.2 to 11.2 steps. It also beats outcome-only GRPO on every difficulty level.
