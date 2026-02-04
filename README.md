# Align-LLMRec: Semantic Alignment for Prompt-based Recommendations with LLMs


## Overview
**Align-LLMRec** addresses three fundamental challenges in modern recommendation systems:
* **Information Under-utilization**: Jointly models interaction data with semantic signals from item metadata and user reviews.
* **Cold-start Problem**: Enhances performance for new or rare items using contrastive learning and semantic alignment.
* **Sparse/Noisy Data**: Leverages LLMs and denoised representations to provide robust, context-aware predictions.

---

## Structure
The structure of this project is:
```text
Align-LLMRec/
├── data/               # Processing for Amazon Music, Books, and Electronics 
├── models/             # SBERT, DistilBERT, and Transformer CF Backbone 
├── stages/
│   ├── stage1_rec.py   # Sentiment-aware representation learning 
│   └── stage2_llm.py   # LLM-compatible embedding alignment 
├── utils/              # Contrastive loss and cross-attention fusion 
└── requirements.txt    # Dependencies (PyTorch, Transformers, etc.)
