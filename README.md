# **LiveCodeBench (Custom Setup)**

This repository contains a **customized version of the LiveCodeBench evaluation framework**, tailored for running and debugging smaller open-source code models (e.g., DeepSeek-Coder-1.3B-Instruct) on limited GPU memory systems. The official repository was cloned onto a local system, and the following changes have been made to the source code.

---

## **Overview**

LiveCodeBench is a benchmark for evaluating code-generation models across programming challenges.  
This fork includes modifications for **easier local evaluation** and **fine-grained control** over model behavior.

---

## **Key Modifications**

- **Custom `vllm_runner.py`:**
  - Added `max_model_len=4096`, `gpu_memory_utilization=0.8`.
  - Integrated caching and batch-size control for smaller GPUs (`--use_cache`, `--cache_batch_size`).

- **Limited Debug Evaluation Mode:**
  - Supports quick evaluation of a subset of problems with `--debug`.

- **Custom Token Control:**
  - Adjusted `max_tokens` in `SamplingParams` to allow longer completions.

---

## **Sample Evaluation command**

python -m lcb_runner.runner.main \
    --model deepseek-ai/deepseek-coder-1.3b-instruct \
    --scenario codegeneration \
    --evaluate \
    --release_version release_v5 \
    --use_cache \
    --cache_batch_size 1 \
    --n 1 \
    --debug

