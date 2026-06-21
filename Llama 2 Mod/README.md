#  Retail Chatbot for a Chocolate Retail Business 

Fine tuned model link: https://drive.google.com/drive/folders/171I3cCbr3BONz7w71wA8_349xP-ACFOJ?usp=sharing

This project features a chatbot built using Meta’s LLaMA2 7B model, fine-tuned via QLoRA on 1000 QnAs tailored for a premium chocolate retail business.

The chatbot can answer questions related to:
- Gifting, packaging, and shipping
- Sugar levels, dietary needs, daily consumption
- Bulk orders, international queries, and more

---
## Technologies & Tools Used

| Category      | Tool / Library                            |
|---------------|-------------------------------------------|
| Base Model    | `meta-llama/Llama-2-7b-chat-hf` (Hugging Face) |
| Fine-Tuning   | `QLoRA` (LoRA + 4-bit quantization)       |
| Libraries     | `transformers`, `peft`, `trl`, `bitsandbytes` |
| Platform      | Google Colab (T4 / A100 GPU)              |
| Format        | Prompt-tuned using `[INST]...[/INST]` style |
| Inference     | Python CLI (`runbot.py`)                  |

---

## Dataset Overview

- Total QnAs: **1000**
- Topics: Product info, gifting, packaging, health queries, pricing, bulk orders, and emotional tones (funny, clever, confused, formal, casual)

---

##  Model Training & Evaluation for LLaMA2 7B model

| Metric           | Value     |
|------------------|-----------|
| Final Loss       | 0.2323    |
| Perplexity       | 1.26      |
| Token Accuracy   | 72.93%    |
| Exact Match Score| 100%      |
| Epochs           | 15        |
| Eval Set Size    | 118 QnAs  |

Training was done using **QLoRA** with `SFTTrainer` from `trl`. LoRA adapters were merged post-training using `.merge_and_unload()` to make the model self-contained.

---

## 📁 Folder Structure
```plaintext
Llama-Retail-Chatbot/
├── data-files/
    ├── train.txt                        # Training set   (formatted QnAs)
    ├── test.txt                         # Test set       (formatted QnAs)
    └── validation.txt                   # Validation set (formatted QnAs)                         
├── Llama_model_for_Retail_Business.py   # Colab notebook for QLoRA fine-tuning
├── README.md                            # Project documentation             
├── requirements.txt                     # Full environment for Colab fine-tuning
├── requirements_minimal.txt             # Minimal dependencies for running the bot
├── runbot.py                            # Command-line chatbot for local inference

```

---

## 🛠️ Setup Instructions for LLaMA2 7B model

#### 1. Install dependencies

pip install -r requirements.txt

####  2.📥 Download the Fine-Tuned Model

1. The fine-tuned model is too large for GitHub, so please download it manually from Google Drive: https://drive.google.com/file/d/1jKaaXJ31wHnbciCGqBXg-HZeI-10uZdZ/view?usp=sharing
2. Unzip the file
3. Copy the merged model folder llama2-erote-final/ into the root directory
Llama-Retail-Chatbot/
├── llama2-erote-final/
├── runbot.py

#### 3. Run the chatbot
python runbot.py



### ✨ Features
Supports GPT-style responses with temperature and top-p sampling

Works offline after fine-tuning (no need for API)

Format-ready for future RAG integration

Can be converted to Streamlit, Gradio, or web chat UI

---

### ⚠️ Limitations & Disclaimer

- This chatbot is trained on a **synthetic dataset** of 1000 QnAs generated from a small base of handcrafted inputs. While great care was taken to simulate realistic customer queries, some responses may not fully reflect complex or edge-case scenarios.
- The model was fine-tuned using open-source tools and may inherit **biases or hallucinations** present in the base LLaMA-2 model.
- This chatbot is designed for **informational and demonstration purposes** only. It should not be used for medical, legal, or financial advice.
- International pricing, shipping timelines, or allergen-specific answers may not always be accurate — users are encouraged to contact the business directly for final confirmation.
- The creators are not responsible for any misinterpretation or misuse of the chatbot’s responses in real-world applications.

---
