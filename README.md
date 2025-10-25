# **LiveCodeBench (Custom Setup)**

This repository contains a **customized version of the LiveCodeBench evaluation framework**, tailored for running and debugging smaller open-source code models (e.g., DeepSeek-Coder-1.3B-Instruct) on limited GPU memory systems.

---

## **Overview**

LiveCodeBench is a benchmark for evaluating code-generation models across programming challenges.  
This fork includes modifications for **easier local evaluation** and **fine-grained control** over model behavior.

---

## **⚙️ Key Modifications**

- **Custom `vllm_runner.py`:**
  - Added `max_model_len=4096`, `gpu_memory_utilization=0.8`.
  - Integrated caching and batch-size control for smaller GPUs (`--use_cache`, `--cache_batch_size`).

- **Limited Debug Evaluation Mode:**
  - Supports quick evaluation of a subset of problems with `--debug`.

- **Custom Token Control:**
  - Adjusted `max_tokens` in `SamplingParams` to allow longer completions.

---
