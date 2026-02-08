# 🇻🇳 Vietnamese UN Delegate Speech Fine-Tuning (Mistral-7B)

This project fine-tunes **Mistral-7B-0.1-Instruct** to replicate the speaking style, tone, and structure of **Vietnamese delegates’ speeches at United Nations conferences**.

The goal is to generate responses that reflect Vietnam’s diplomatic voice, including formal language, multilateral perspectives, and UN-style rhetoric.

---

## 📌 Project Overview

* **Base model**: `Mistral-7B-0.1-Instruct`
* **Fine-tuning method**: **QLoRA** (parameter-efficient fine-tuning)
* **Domain**: Diplomatic speeches by Vietnamese representatives at the UN
* **Language**: English (official UN speech transcripts)

---

## 📂 Project Structure

```
.
├── finetune-data/
│   └── ... (speech data scraped from vietnam.un.org)
│
├── Vietnam_delegate_finetuned.ipynb
├── Vietnam_delegate_run.ipynb
└── README.md
```

---

## 🗂 Dataset

* **Source**:
  Official speech transcripts from
  👉 [https://vietnam.un.org/en/press-centre/speeches](https://vietnam.un.org/en/press-centre/speeches)

* **Content**:

  * Statements at UN General Assembly
  * Remarks on sustainable development, peace, security, climate change, and multilateral cooperation
  * Formal diplomatic language consistent with UN conventions

* **Location**:
  All processed training data is stored in `/finetune-data`.

---

## 🔧 Fine-Tuning Details

The fine-tuning process is implemented in:

```
Vietnam_delegate_finetuned.ipynb
```

Key characteristics:

* Uses **QLoRA** for memory-efficient training
* Adapts only low-rank parameters while keeping the base model frozen
* Suitable for limited GPU resources (e.g. Colab / single GPU)

The notebook covers:

* Data preprocessing
* Prompt formatting
* Model loading with quantization
* Training configuration
* Saving the fine-tuned adapter

---

## 🚀 Running the Fine-Tuned Model

Example inference and evaluation are provided in:

```
Vietnam_delegate_run.ipynb
```

This notebook demonstrates:

* How to load the fine-tuned model
* Sample prompts and generated speeches
* **LLM-as-a-judge evaluation**, where another LLM is used to assess:

  * Diplomatic coherence and structure
  * Policy accuracy
  * Cultural and tylistic alignment with Vietnamese UN speeches
  * Technical quality

## ⚠️ Disclaimer

This project is for **research and educational purposes only**.

* The generated content does **not** represent official statements by the Government of Vietnam.
* Outputs should not be used for real diplomatic, political, or governmental communications.
