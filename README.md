#Align-LLMRec: Semantic Alignment for Prompt-based Recommendations with LLMs

**Overview
Align-LLMRec is a unified recommendation framework that integrates classical collaborative filtering (CF) with the reasoning capabilities of Large Language Models (LLMs). It specifically addresses:
Information Under-utilization: Leverages item metadata and user-generated review sentiment.
Cold-Start & Sparsity: Uses contrastive alignment to produce robust embeddings even for items with limited history.
Reasoning: Employs an LLM-compatible embedding interface for interpretable, prompt-based recommendations.

**Architecture
The framework operates in two distinct training stages:
Stage I (Representation Learning): Jointly optimizes a sequential CF backbone with SBERT (metadata) and DistilBERT (reviews) encoders using a cross-attention fusion mechanism.
Stage II (LLM Alignment): Trains a lightweight projection interface to map learned embeddings into the latent space of a frozen LLM.
