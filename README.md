
# 🍻 Beer Cap Recognition via Deep Metric Learning

A deep learning system for recognizing beer cap brands using visual similarity and metric learning. This project handles over 150 beer brands, many with high intra-class variance and minimal supervision, and achieves strong performance in both seen and novel class evaluations.

---

## 🚀 Overview

This project uses **deep metric learning** to create embeddings for beer cap images and perform **image retrieval-based brand recognition**. It is designed to work in real-world conditions where new, unseen beer caps may appear and must be matched to similar known brands.

---

## 🧠 Model & Training

- **Backbone**: Pretrained CNN (`EmbeddingNet`) with frozen batch norm  
- **Loss**: `MultiSimilarityLoss` (α=17.97, β=98.89, base=0.39)  
- **Mining**: `MultiSimilarityMiner` (ε=0.32)  
- **Embedding size**: Configurable  
- **Frameworks**: PyTorch, PyTorch Metric Learning, Faiss

Training includes:
- Balanced P-K batch sampling across 150+ brands
- Reproducible data splits (train/val/test)
- Hard sample mining during training

---

## 📊 Performance

### 📦 Seen Brands (100 classes)
- **Recall@1**: 95.76%  
- **Recall@3**: 96.35%  
- **Recall@5**: 96.71%  
- ✅ 97 brands classified as *"Good"*
- 🟡 4 brands with moderate recognition
- ❌ 0 brands classified as "Bad"

### ✨ Novel Brands (Unseen During Training)
- **Recall@1**: 71.34%  
- **Recall@3**: 75.57%  
- **Recall@5**: 77.18%  
- Gallery Size: 4,671 samples  
- Query Size: 4,466 samples  
- 150 query classes (1 skipped due to insufficient data)

---

## 📁 Project Structure

```
.
├── dataset/                 # Beer cap images organized by brand
├── caps_v4.2.ipynb          # Training and evaluation notebook
├── caps_v4.2_bench.txt      # Benchmark results
├── README.md                # Project documentation
└── ...
```

---

## 🔍 Applications

- beer cap identifier
- Visual product search
- Collector database management
- Low-shot learning systems

---

## 📌 Future Work
  
- Few-shot adaptation for novel caps  
- Semantic profile linkage to beer attributes (taste, aroma, etc.)

---
