🗣️ Conversational Text Summarization
Abstractive vs Extractive Analysis on Dialogue Data
📌 Overview
This project presents a comparative analysis of abstractive and extractive summarization techniques applied to conversational (dialogue) text. The goal is to understand how model choice and domain alignment affect summary quality when working with informal, multi-speaker conversations.
The project emphasizes reasoned model selection, reproducibility, and transparent discussion of limitations rather than over-optimization.

🎯 Objectives

Apply an abstractive transformer-based model to dialogue summarization
Build a lightweight extractive summarization baseline
Compare outputs against human-written summaries
Analyze stylistic and semantic differences between approaches
Highlight the impact of domain mismatch in NLP models

📂 Dataset
Type: Conversational dialogues with gold human summaries

Columns:
dialogue: Multi-turn conversation

summary: Human-written reference summary

The dataset contains informal language, short utterances, and implicit context, making it a challenging benchmark for standard summarization models.

🧠 Methods
1️⃣ Abstractive Summarization

Model: facebook/bart-large-cnn (Hugging Face Transformers)

Strengths:
Captures high-level semantic meaning
Produces fluent paraphrases
Observed Limitation:
Introduces reported-speech artifacts (e.g., “says…”) when applied to dialogue
This behavior reflects news-domain pretraining, highlighting domain mismatch
These limitations are intentionally preserved and documented rather than post-hoc corrected.

2️⃣ Extractive Summarization

Approach: Rule-based sentence scoring using word frequency

Design choices:

Simple sentence splitting (no external NLP tokenizers)
Top-N sentence selection (N = 2)
Fully reproducible and lightweight

Strengths:

Faithful to original dialogue
Better stylistic alignment with conversational summaries

🔍 Key Findings

Aspect	                Abstractive  	Extractive
Semantic abstraction	    High	        None
Stylistic fidelity	     Moderate	      High
Hallucination risk	     Present	      None
Dialogue suitability	   Moderate	      High
Interpretability	        Lower	        High

Conclusion:
For conversational datasets, extractive summarization often aligns more closely with human intent, while abstractive models trade stylistic accuracy for semantic richness.

📊 Example Comparison

The notebook presents a clear side-by-side comparison of:

Original dialogue

Human reference summary

Extractive summary

Abstractive summary (with documented limitations)

This makes the trade-offs between approaches immediately visible.

🛠️ Tools & Technologies

Python
Pandas
Hugging Face Transformers
Regular Expressions
Jupyter Notebook

🔁 Reproducibility

No GPU required
No private or gated models
No hard-coded credentials
Notebook runs top → bottom without errors

🚀 Future Work

Fine-tuning abstractive models on dialogue-specific datasets
Automatic evaluation using ROUGE
Hybrid extractive–abstractive pipelines
Speaker-aware summarization



This project demonstrates that model complexity alone does not guarantee better results. For dialogue-heavy data, simpler extractive approaches can outperform large abstractive models when domain alignment and faithfulness are prioritized.
