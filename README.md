<div align="center">

# नमस्ते, I'm Alina Shrestha 👋

**MSc Business Data Science · Aalborg University, Denmark**
*Originally from Kathmandu, Nepal 🇳🇵*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/alina-shrestha-a0ba67270)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:alina1999shrestha@gmail.com , ashre25@student.aau.dk)
[![HuggingFace](https://img.shields.io/badge/🤗_HuggingFace-alinashrestha-FFD21E?style=for-the-badge)](https://huggingface.co/alinashrestha)

</div>

---

## 🧠 About Me

I'm a second-semester MSc student specialising in **Data Engineering and Machine Learning Operations in Business**. I enjoy building end-to-end data pipelines, working with APIs, and exploring how LLMs can be applied in real-world business contexts.

Currently focused on:
- 🤖 Fine-tuning LLMs with parameter-efficient methods (QLoRA, LoRA)
- 🏭 Building multi-agent systems (MAS) with Human-in-the-Loop pipelines
- 📊 Active learning and data-centric AI workflows

---

## 🛠 Tech Stack

**Languages & Libraries**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![scikit--learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)

**Tools & Platforms**

![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=github-actions&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)
![SLURM](https://img.shields.io/badge/SLURM-HPC-green?style=flat-square)
![CrewAI](https://img.shields.io/badge/CrewAI-Agents-purple?style=flat-square)

---

## 📂 Featured Projects

---

### 🌿 Green Patent Classification — Applied Deep Learning (M4 Final)

> *Can an AI system identify genuinely green technology patents — and keep improving itself?*

A full end-to-end **active learning pipeline** that combines uncertainty sampling, multi-agent debate, QLoRA fine-tuning, and Human-in-the-Loop validation to classify 1.5M+ patent claims as green technology or not — with progressively improving accuracy across 3 assignment iterations.

**The Journey: 3 Assignments → 1 Final System**

| | Assignment 2 | Assignment 3 | M4 Final |
|---|---|---|---|
| LLM System | Single Qwen agent | 3-agent Mistral MAS | 3-agent QLoRA Mistral MAS |
| Prompting | Zero-shot | Zero-shot | Few-shot (5 examples) |
| Domain Knowledge | None | None | Fine-tuned on 30k patents |
| Human Reviews | 100/100 claims | 100/100 claims | **11/100 claims only** |
| Gold F1 Score | 0.1053 | 0.4179 | **0.5376 ✨** |

**M4 Final Pipeline:**

```
1.5M Patents (Y02 columns)
        ↓
Silver Label Generation (50k balanced dataset)
        ↓
Uncertainty Sampling → Top 100 hardest claims
        ↓
QLoRA Fine-tuned Mistral-7B (30k silver patents)
        ↓
3-Agent MAS: Advocate → Skeptic → Judge
        ↓
Auto-classified: 89 claims  |  HITL flagged: 11 claims
        ↓
Final Gold Dataset (100 labels: 35 GREEN, 65 NOT GREEN)
        ↓
PatentSBERTa Fine-tuning → Silver F1: 0.8055 | Gold F1: 0.5376
```

**Key Technical Highlights:**
- 🔧 **QLoRA fine-tuning** of Mistral-7B-Instruct-v0.2 — only **0.58% of parameters trained** (41M / 7.2B), 4-bit NF4 quantisation, trained on NVIDIA L4 GPU in 27 minutes
- 🤖 **3-agent debate system** — Advocate argues FOR green → Skeptic argues AGAINST → Judge outputs JSON verdict with confidence score
- 📍 **Few-shot prompting** — 5 domain-specific examples per agent, grounded in Y02 patent taxonomy
- 🎯 **HITL threshold** — confidence < 0.65 flags claim for human review → 89% automation achieved
- 💾 **Fault-tolerant checkpointing** — auto-save every 5 claims, recovered from SSH disconnection at step 725
- 📈 **PatentSBERTa fine-tuning** — 30,100 training examples (30k silver + 100 gold), smooth loss: 0.61 → 0.43

**Models on HuggingFace 🤗**

[![PatentSBERTa M4](https://img.shields.io/badge/🤗-patentsbert--m4--final-FFD21E?style=flat-square)](https://huggingface.co/alinashrestha/patentsbert-m4-final)
[![QLoRA Mistral](https://img.shields.io/badge/🤗-qlora--mistral--y02--v2-FFD21E?style=flat-square)](https://huggingface.co/alinashrestha/qlora-mistral-y02-v2)
https://huggingface.co/alinashrestha/activity/all

`Python` `PyTorch` `HuggingFace` `QLoRA` `PEFT` `CrewAI` `PatentSBERTa` `Mistral-7B` `SLURM` `Active Learning`

---

### 🌤 Automated Weather Pipeline

> *Daily weather meets poetry — in two languages.*

An automated data pipeline that collects daily weather forecasts for three cities, stores data in SQLite, generates a bilingual (English + Nepali) poem using the Groq LLM, and publishes the result via GitHub Pages — all orchestrated with GitHub Actions.

**How it works:**
```
Open-Meteo API → Python script → SQLite storage
      ↓
Groq LLM → Bilingual poem (English + Nepali)
      ↓
GitHub Actions (daily schedule) → GitHub Pages
```

🔗 [Live Site](add-your-live-site-link)

`Python` `Open-Meteo API` `SQLite` `Groq LLM` `GitHub Actions` `GitHub Pages`

---
### 📰 [Danish News AI Classification & Topic Modeling](https://github.com/alina1999shrestha-blip/Semester_project_M3)
> End-to-end NLP pipeline on a large Danish news dataset (2016–2024) from Hugging Face. Classified articles by news category and AI-relevance using **zero-shot** and **few-shot** NLI models, validated with confusion matrices, and performed **topic modeling** using BERTopic with sentence embeddings to uncover hidden themes in AI-related news.

**Tech:** Python · Pandas · HuggingFace Transformers · BERTopic · SentenceTransformers · UMAP · HDBSCAN · Ollama · Matplotlib · Seaborn

---

## 📊 What I've Learned Building These Projects

```## 📖 What I've Learned Building These Projects
```python
lessons = {
    # M4 - Patent Claims
    "always_version_your_models":      "V1 failed, V2 succeeded — save checkpoints!",
    "silver_labels_have_a_ceiling":    "~15% noise → F1 plateaus at 0.80 no matter what",
    "domain_knowledge_matters":        "Gold F1: 0.10 → 0.54 just by fine-tuning the LLM",
    "less_human_work_more_ai":         "11 reviews instead of 100 = same quality, 89% less effort",
    "smooth_loss_curves_are_poetry":   "0.87 → 0.83, every step learning something new",
---
    # M3 - Danish News NLP
    "nlp_at_scale_is_hard":            "Classifying 280K+ Danish articles taught me to chunk smartly",
    "zero_shot_has_limits":            "mDeBERTa performs well but ~15% noise is hard to overcome",
    "topic_modeling_reveals_patterns": "BERTopic + UMAP uncovered hidden AI themes in Danish news",
---
    # M5 - Weather Pipeline
    "automate_everything":             "GitHub Actions runs my pipeline daily — no manual work needed",
    "apis_are_powerful":               "Open-Meteo + Groq API = real data + AI poem in under 30 seconds",
    "llms_speak_many_languages":       "LLaMA 3.3 generated fluent Nepali poetry from weather numbers",
}
---

## 💡 Interests

- 📊 Data Engineering & Pipelines
- 🤖 Machine Learning Operations (MLOps)
- 🔗 API Integration & Automation
- 🧠 LLM Fine-tuning & Agentic AI Systems
- 📈 Data-driven Business Decision Making

---

<div align="center">

*Thanks for visiting! Feel free to explore my repositories.* 🚀

![Profile views](https://komarev.com/ghpvc/?username=your-github-username&color=brightgreen&style=flat-square)

</div>
