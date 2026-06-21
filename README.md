# Chocolate Retail QnA Chatbot – LLaMA2-7B

This repository contains two domain-specific chatbots for a premium chocolate retail business — built using **Meta’s LLaMA2-7B (via QLoRA)** and **OpenAI’s GPT-2** models.

The bots are trained on 1000 QnAs to handle queries related to:

-  Gifting, packaging, freshness, pricing  
-  Dietary needs, daily consumption  
-  Bulk orders, international questions  
-  Casual, funny, emotional tones and more

---

## 📁 Repository Structure

```
Retail-QnA-Chatbot-LLaMA2-GPT2/
├── GPT2_Model/              ← GPT-2 based chatbot
├── LLaMA2_Model/            ← LLaMA2-7B QLoRA chatbot (better performance)
├── INSTRUCTIONS.md          ← Intruction to run Chatbot on your system locally
├── README.md                ← You're here!

```

---

## ⚖️ Model Comparison Summary

| Metric                || LLaMA2-7B (QLoRA)       |
|-----------------------|--------------------------|
| Validation Loss       | 0.1156                   |
| Perplexity            | 1.12                     |
| Accuracy (Exact Match)| 100.00%                  |
| Output Quality        | Highly contextualized    |
| Recommended For Use   | ✅ Yes                   |

> 🔍 GPT-2 is included for comparison purposes only.  
👉 **Please use the `LLaMA2_Model` folder for best results.**

---

## 🧠 Tech Stack

- Transformers, TRL, PEFT, Bitsandbytes  
- QLoRA for 4-bit fine-tuning on LLaMA2  
- Python + Google Colab  
- Dataset: Curated synthetic QnA pairs  

---

## 📥 Fine-Tuned Model Access

The LLaMA2 model is too large for GitHub.

🔗 [Download LLaMA2 fine-tuned model (.pt) here](https://drive.google.com/drive/folders/171I3cCbr3BONz7w71wA8_349xP-ACFOJ?usp=drive_link)

Instructions for setup are included in the `LLaMA2_Model/README.md`.

---


