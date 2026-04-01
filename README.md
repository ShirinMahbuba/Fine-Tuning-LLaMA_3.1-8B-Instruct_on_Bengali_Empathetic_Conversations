LLaMA 3.1-8B Fine-Tuning for Bengali Empathetic Conversations
This repository contains the solution for the AI Engineer Task (Test 2). The goal is to fine-tune a LLaMA 3.1-8B model to generate empathetic responses in Bengali using Parameter-Efficient Fine-Tuning (PEFT) techniques.

🚀 Project Overview
Model: unsloth/meta-llama-3.1-8b-bnb-4bit.
Task: Fine-tuning on the Bengali Empathetic Conversations dataset.
Environment: Developed and trained on Kaggle Free GPU.

🛠️ Tech Stack & Optimization
Library:Hugging Face transformers, peft, trl, bitsandbytes.
Fine-tuning Technique: LoRA (Low-Rank Adaptation).
Resource Optimization:
* 4-bit Quantization (BNB)
* .Gradient Checkpointing
* .Mixed Precision Training (FP16).

🏗️ Architecture (OOP Design)
The project is modularized into three core classes:
DatasetProcessor: Handles data cleaning and template formatting for Llama-3 instruction fine-tuning.
LLAMAFineTuner: Manages model loading, LoRA configuration, and the SFT (Supervised Fine-Tuning) process.
Evaluator: Calculates NLP metrics (BLEU, ROUGE) and logs results into an SQLite database.

📊 Evaluation Results
The final metrics and sample responses are stored in assessment_results.db:
Metric                     Value
Training Loss              0.902142
BLEU Score                 0.0 (Due to short training steps & specific reference matching)
ROUGE-L                    0.0

Sample Response:
Input: "আমার খুব একা লাগছে, আমি কি করতে পারি?"
AI Output: "আমি মনে করি আপনার জন্য এটি খুব সম্ভব। আপনি কি..."

📁 Repository Structure
llama_finetuning.ipynb: The main Kaggle notebook.
assessment_results.db: SQLite database containing the experiment logs.
README.md: Project documentation.

📺 Video Explanation

