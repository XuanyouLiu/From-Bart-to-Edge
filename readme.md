# CIS5300 Final Project: From BART to Edge

Fine-tuning Large Language Models (LLMs) for **Chinese-to-English translation** in the **education domain**, comparing **mBART** and **M2M100**, utilizing **LoRA** and **Layer Freezing** techniques to optimize performance and efficiency.

---

## Project Overview

**Objective:** Identify the most effective and resource-efficient fine-tuning technique for domain-specific Chinese-to-English translation.

**Models Compared:**
- [mBART-50](https://huggingface.co/facebook/mbart-large-50) (Multilingual BART)
- [M2M100](https://huggingface.co/facebook/m2m100_418M) (Many-to-Many Multilingual Model)

**Techniques Implemented:**
- **LoRA (Low-Rank Adaptation)**
- **Layer Freezing**
- **Quantization (LLaMA & Marian MT)**

## Project Structure

The repository contains two main Jupyter notebooks:
- `Education_Translation.ipynb` → Fine-tuning in the **education** domain
- `Science_Translation.ipynb` → Fine-tuning in the **science** domain

### Pipeline Overview

1. **Load & Preprocess**: Import libraries, load datasets, initialize models, define evaluation metrics.
2. **Baseline Evaluation**: Evaluate pre-trained models (mBART & M2M100) on a **50,000-sample dataset**.
3. **Hyperparameter Tuning**: Grid search on a smaller **10,000-sample dataset** to find optimal settings.
4. **Fine-Tuning**: Apply best parameters for LoRA and Layer Freezing on the **full dataset**.
5. **Evaluation & Analysis**: Compare BLEU scores, perform error analysis, and measure GPU usage.
6. **Extensions**: Explore **quantization** using **LLaMA** and **Marian MT** for low-resource scenarios.

---

## Setup & Installation

### 1. Install Dependencies

Ensure the following libraries are installed:

```bash
pip install datasets optimum auto-gptq sentencepiece bitsandbytes sacremoses sacrebleu transformers peft nltk tqdm pandas torch
