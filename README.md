# Align-LLMRec: Semantic Alignment for Prompt-based Recommendations with LLMs


## Overview
**Align-LLMRec** addresses three fundamental challenges in modern recommendation systems:
* **Information Under-utilization**: Jointly models interaction data with semantic signals from item metadata and user reviews.
* **Cold-start Problem**: Enhances performance for new or rare items using contrastive learning and semantic alignment.
* **Sparse/Noisy Data**: Leverages LLMs and denoised representations to provide robust, context-aware predictions.

---

## 🏗️ Architecture
Align-LLMRec is a hybrid CF-LLM framework that integrates parallel encoding paths for user interactions, item metadata, and reviews. The system is built upon three core pillars:

### **1. Cross-attention Fusion**
This module extracts and merges complementary signals from textual data:
* **SBERT (Sentence-BERT)**: Encodes item metadata (titles and descriptions) to capture concise semantic information.
* **DistilBERT**: Processes user reviews to extract subjective opinions and affective sentiment.
* **Cross-Attention**: Dynamically fuses these embeddings, allowing the model to adaptively weight semantic vs. affective cues based on user intent.

### **2. Contrastive CF Backbone**
The collaborative core of the model utilizes a Transformer-based sequential architecture:
* **Behavioral Modeling**: Captures temporal patterns and evolving user preferences from historical interaction data.
* **Semantic Alignment**: Employs a contrastive objective to align these behavioral embeddings with the fused textual representations, ensuring the CF core is "anchored" to stable semantic features.

### **3. LLM-Compatible Interface**
A lightweight bridge that enables generative, context-aware recommendations:
* **Latent-to-Text Projection**: Employs trainable MLPs to project learned CF embeddings into the LLM-compatible token space.
* **Soft Prompting**: The projected embeddings act as soft prompt tokens that condition a frozen, pretrained LLM.
* **Reasoning & Output**: This design enables the LLM to generate recommendations and explanations grounded in both collaborative behavior and sentiment-rich metadata.
