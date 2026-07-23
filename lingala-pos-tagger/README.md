# Natively Fine-Tuning AfroXLM-R for Lingala Part-of-Speech Tagging

**Author:** Van Tasi  
**Framework:** PyTorch, Hugging Face Transformers & PEFT  
**Base Model:** `Davlan/afro-xlmr-large` (550M Parameters)

---

## Overview

This project investigates parameter-efficient fine-tuning of **AfroXLM-R** for **Lingala Part-of-Speech (POS) tagging**, a task constrained by the severe lack of high-quality annotated corpora for low-resource Bantu languages. Instead of relying on cross-lingual projection—which often introduces morphological inconsistencies—we bootstrap a native silver-standard corpus generated under strict linguistic constraints, providing word-level Universal POS annotations specifically for Lingala.

A key challenge arises from the mismatch between word-level annotations and the transformer's SentencePiece tokenizer. To preserve label integrity during training, only the first subword of each token contributes to the optimization objective, while subsequent fragments are masked (`-100`) and excluded from the loss calculation. The model itself is adapted using **Low-Rank Adaptation (LoRA)**, allowing the 550M-parameter backbone to be fine-tuned within modest hardware constraints by freezing the pretrained weights and learning only lightweight adapter matrices.

---

## Training Pipeline

The pipeline begins by cleaning and validating the generated corpus before tokenization and subword-label alignment. LoRA adapters are then attached to the token classification head, after which the model is fine-tuned using mixed-precision training (`fp16`), micro-batching, and gradient accumulation to remain within a 15 GB VRAM budget. Throughout training, the model is evaluated after every epoch using **seqeval**, tracking Precision, Recall, Accuracy, and Macro F1 across the Universal POS tagset.

---

## Results

Training converged smoothly, with both training and validation loss indicating stable optimization and no significant signs of overfitting. The final model achieved **91.2% accuracy** and an **89.5% Macro F1 score**. Additional analysis through per-class classification reports and confusion matrices provides a more detailed view of the model's strengths and the remaining sources of linguistic ambiguity.
