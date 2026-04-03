
# 🤖 LLaMA 3.1-8B Fine-Tuning for Bengali Empathetic Conversations

This repository contains the solution for the **AI Engineer Task (Test 2)**. The project focuses on fine-tuning a LLaMA 3.1-8B model to generate empathetic responses in Bengali using Parameter-Efficient Fine-Tuning (PEFT).

## 📋 Table of Contents

1.  [Project Overview](https://www.google.com/search?q=%23-project-overview)
2.  [Technical Specifications](https://www.google.com/search?q=%23-technical-specifications)
3.  [Architecture & Design Patterns](https://www.google.com/search?q=%23-architecture--design-patterns)
4.  [Training & Optimization](https://www.google.com/search?q=%23-training--optimization)
5.  [Evaluation & Results](https://www.google.com/search?q=%23-evaluation--results)
6.  [Challenges Faced](https://www.google.com/search?q=%23-challenges-faced)
7.  [Repository Structure](https://www.google.com/search?q=%23-repository-structure)
8.  [Explanation Video](https://www.google.com/search?q=%23-explanation-video)

-----

## 🚀 Project Overview

  * **Objective**: To develop an AI model capable of generating culturally relevant and empathetic responses in Bengali.
  * **Base Model**: `unsloth/meta-llama-3.1-8b-bnb-4bit`.
  * **Dataset**: Bengali Empathetic Conversations Corpus.

## 🛠 Technical Specifications

  * **Frameworks**: PyTorch, Hugging Face `transformers`, `peft`, `trl`, `bitsandbytes`.
  * **Method**: **LoRA (Low-Rank Adaptation)** for efficient weight updates.
  * **Hardware**: Trained on **Kaggle Free P100 GPU** environment.

## 🏗 Architecture & Design Patterns

The solution follows **Object-Oriented Programming (OOP)** principles and incorporates the **Strategy Pattern** for modularity:

  * **`DatasetProcessor`**: Responsible for data cleaning and formatting into Llama-3 instruction templates.
  * **`LLAMAFineTuner`**: Handles model initialization, LoRA injection, and the SFT (Supervised Fine-Tuning) pipeline.
  * **`Evaluator`**: Calculates NLP metrics (BLEU, ROUGE) and manages the SQLite logging system.

## ⚡ Training & Optimization

To handle the large model size on limited hardware, the following optimizations were implemented:

  * **4-bit Quantization (BNB)**: Significantly reduced VRAM consumption.
  * **Gradient Checkpointing**: Enabled to save memory during the backward pass.
  * **Mixed Precision (FP16)**: Used to accelerate training and reduce compute overhead.

## 📊 Evaluation & Results

All experiment logs and generated responses are stored in `assessment_results.db`.

  * **Training Loss**: 0.91284
  * **Metrics**: BLEU and ROUGE-L scores were calculated (currently 0.0 due to short training steps and specific token matching).
  * **Sample Input**: "আমার খুব একা লাগছে, আমি কি করতে পারি?" (I feel very lonely, what can I do?).
  * **Model Output**: "আমি মনে করি আপনার জন্য এটি খুব সম্ভব। আপনি কি..." (I think it is very possible for you. Do you...).

## ⚠️ Challenges Faced

  * **Sequence Length**: Adjusted to 256 to prevent Out-of-Memory (OOM) errors on Kaggle's GPU.
  * **Cache Conflicts**: `use_cache` was set to `False` to ensure compatibility with Gradient Checkpointing.

## 📂 Repository Structure

  * `llama_finetuning.ipynb`: The primary training notebook.
  * `assessment_results.db`: SQLite database containing `LLAMAExperiments` and `GeneratedResponses` tables.
  * `README.md`: Project documentation.

## 📺 Explanation Video

[**Insert your YouTube/Google Drive link here**]

