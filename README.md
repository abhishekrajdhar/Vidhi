````markdown
# 🩺 Vidhi v1 — Healthcare Small Language Model (SLM)

Vidhi v1 is a lightweight healthcare-focused Small Language Model (SLM) designed for biomedical reasoning, medical question answering, and assistant-style healthcare conversations.

The project explores the complete lifecycle of building a domain-specific language model from scratch:
- custom transformer architecture
- biomedical pretraining
- reasoning fine-tuning
- medical instruction tuning
- assistant-style inference

---

# 🚀 Project Vision

The goal of Vidhi is to create an efficient and domain-adapted medical language model capable of:
- understanding biomedical language
- answering healthcare-related questions
- generating concise medical explanations
- serving as a foundation for future medical AI assistants

Vidhi is designed as an educational and research-focused project demonstrating how modern domain-specific SLMs are built.

---

# 🧠 Model Overview

| Feature | Details |
|---|---|
| Model Name | Vidhi v1 |
| Architecture | Decoder-only Transformer |
| Parameters | ~64 Million |
| Framework | PyTorch |
| Tokenizer | GPT-2 Tokenizer (`tiktoken`) |
| Context Length | 512 tokens |
| Training Type | Autoregressive Language Modeling |
| Domain | Healthcare / Biomedical NLP |

---

# 🏗️ Architecture

Vidhi uses a custom GPT-style decoder-only transformer architecture implemented from scratch in PyTorch.

## Core Components

### 1. Token Embeddings
Maps token IDs into dense vector representations.

### 2. Positional Embeddings
Learned positional embeddings allow the model to understand token order within the context window.

### 3. Multi-Head Self Attention
Enables the model to attend to relevant medical concepts and contextual information across long biomedical sequences.

### 4. Feed Forward Networks (MLP)
Applies non-linear transformations to enrich semantic representations.

### 5. Residual Connections + Layer Normalization
Improves optimization stability and gradient flow during training.

### 6. Causal Masking
Ensures autoregressive next-token prediction behavior.

---

# 📚 Training Pipeline

Vidhi v1 was trained in multiple stages.

---

# Stage 1 — Biomedical Pretraining

The model was first pretrained on biomedical literature to adapt it to healthcare terminology and writing styles.

## Dataset Used

### PubMed Biomedical Dataset
Source:
- PubMed research abstracts and biomedical text corpora

Dataset:
- `MedRAG/pubmed`

### Why PubMed?
PubMed contains:
- biomedical terminology
- clinical language
- disease descriptions
- treatment information
- medical research writing patterns

This stage helped Vidhi learn:
- medical vocabulary
- biomedical syntax
- healthcare-specific language structures

---

# Stage 2 — Medical QA Alignment

Vidhi was further fine-tuned using medical multiple-choice question datasets.

## Dataset Used

### MedMCQA
A large-scale medical multiple-choice QA dataset.

Contains:
- medical entrance exam questions
- clinical reasoning MCQs
- medical concepts across multiple specialties

This stage improved:
- medical concept recall
- answer selection
- question understanding

---

# Stage 3 — Biomedical Reasoning Fine-Tuning

The model was trained on biomedical reasoning-style datasets.

## Dataset Used

### PubMedQA
A biomedical QA dataset containing:
- questions
- biomedical context
- long-form reasoning answers

This stage improved:
- biomedical reasoning
- explanation generation
- contextual understanding

---

# Stage 4 — Instruction Tuning

Vidhi was instruction-tuned to improve conversational assistant behavior.

## Dataset Used

### Medical Meadow / MedAlpaca Style Instruction Dataset
Used for:
- assistant-style responses
- healthcare conversations
- instruction-following behavior

This stage improved:
- conversational formatting
- concise explanations
- assistant-style outputs

---

# ⚙️ Training Details

| Component | Value |
|---|---|
| Optimizer | AdamW |
| LR Scheduler | Cosine Decay |
| Precision | FP16 / Mixed Precision |
| GPUs | Dual NVIDIA T4 |
| Framework | PyTorch |
| Gradient Accumulation | Enabled |
| Checkpointing | Best Validation Loss |

---

# 📊 Current Capabilities

Vidhi v1 can:
- answer healthcare questions
- generate biomedical-style explanations
- understand medical terminology
- perform lightweight medical reasoning
- engage in assistant-style healthcare responses

---

# ⚠️ Current Limitations

Vidhi v1 is still an experimental research prototype.

Known limitations:
- may hallucinate medical information
- may generate incorrect clinical statements
- limited reasoning depth due to small parameter size
- lacks retrieval grounding (RAG)
- not suitable for real clinical deployment

This model should NOT be used for:
- diagnosis
- treatment decisions
- emergency healthcare guidance

---

# 🔬 Future Improvements (Vidhi v2)

Planned future work:
- Retrieval-Augmented Generation (RAG)
- larger context windows
- improved instruction tuning
- factuality optimization
- medical benchmark evaluation
- RLHF / preference optimization
- Hugging Face Transformers integration

---

# 🧪 Example Usage

```python
from model import Vidhi, VidhiConfig
import torch

device = "cuda"

config = VidhiConfig()

model = Vidhi(config)

model.load_state_dict(
    torch.load("vidhi_medassist.pt")
)

model.to(device)
model.eval()
````

---

# 🤖 Example Prompt

```text
User:
Why is Metformin considered first-line therapy for Type 2 Diabetes?

Assistant:
```

---

# 🤗 Hugging Face Model

You can explore and download the model here:

👉 https://huggingface.co/abhishekrajdhar/vidhi-v1

---

# 📁 Repository Structure

```text
vidhi-v1/
│
├── model.py
├── train.py
├── inference.py
├── config.json
├── requirements.txt
├── README.md
└── checkpoints/
```

---

# 🛠️ Tech Stack

* PyTorch
* NumPy
* Hugging Face Datasets
* tiktoken
* CUDA
* Kaggle GPUs

---

# 📌 Key Learnings from the Project

This project explores:

* transformer implementation from scratch
* domain adaptation
* biomedical language modeling
* instruction tuning
* reasoning fine-tuning
* multi-stage SLM training pipelines

---

# 🙌 Acknowledgements

Datasets and inspirations:

* PubMed
* MedMCQA
* PubMedQA
* MedAlpaca / Medical Meadow
* GPT-style transformer architectures

---

# 📜 License

This project is released for research and educational purposes only.

---

# 👨‍💻 Author

Abhishek R. Dubey

AI Engineer | Healthcare AI Research | LLM Engineering

---

```
```
