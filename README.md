# LLM-PII-Masking-Synth-Data

PII masking using **synthetic data** for fine-tuning a **small BERT-style language model** (privacy-first workflows for sensitive domains like legal text).

> ⚠️ Privacy note: Fine-tuning on sensitive text can increase the risk of memorization and unintended disclosure. Use synthetic data and strong governance when working with PII-heavy corpora. See: evidence that fine-tuning can leak PII in practice. (Sun et al., 2023)  

## What this repo contains

- **`PII_Legal_LLM.ipynb`** — an end-to-end example notebook that:
  1) generates or loads **synthetic PII-labeled text**
  2) trains / fine-tunes a **small BERT model** for PII entity detection (NER-style)
  3) uses the model to **mask/redact PII** in text
  4) outputs a masked dataset suitable for downstream use (analytics, model training, indexing)

## Why synthetic data + masking?

When your real data contains PII (names, addresses, case numbers, emails, IDs), you typically want:
- a **PII detector** (NER model or hybrid rules + ML)
- a **masking/anonymization step** to prevent private fields from leaking
- optional **synthetic replacements** (instead of `<NAME>`) to preserve linguistic realism for training

This kind of pipeline is commonly recommended for privacy and safety in LLM systems, and synthetic data is an active area for privacy-preserving workflows.
