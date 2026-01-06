# Student-Note Guided LLMs
**Improving Reasoning Consistency, Memory, and Cross-Domain Generalization via External Latent Notes**  

This repository implements a **Student-Note Guided LLM framework** that externalizes intermediate reasoning into structured notes, then iteratively **critiques**, **revises**, and **stores** those notes as an evolving external memory. Instead of updating model parameters, “learning” happens through **note refinement + memory retrieval**.

The project is organized as a step-by-step pipeline (Phase-1/2) and extended with evaluation, ablations, and cross-domain experiments (Phase-3/4/5), plus a formal algorithmic description (Phase-6).

---

## . Key Idea (High Level)

Most LLM inference is stateless: intermediate reasoning is not preserved across tasks, causing:
- inconsistent reasoning under paraphrases,
- weak knowledge carryover,
- uncorrected errors and hallucinations.

**Student-Note Guided LLM** introduces an explicit intermediate artifact: a **structured student note**.  
For each task/topic:
1) generate a note  
2) critique it  
3) revise it  
4) store it in memory  
5) answer questions using **ONLY** the note (and optionally retrieved notes)
---
