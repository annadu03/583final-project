# 583final-project
# Deep Learning on Graph-Structured Data for HIV Inhibitor Prediction

## Overview

This project applies **Graph Neural Networks (GNNs)** to molecular classification tasks, specifically identifying potential HIV inhibitors. Using advanced GNN architectures such as **Graph Convolutional Networks (GCNs)**, **Message Passing Neural Networks (MPNNs)**, and **Graph Attention Networks (GATv2)**, we explore different pooling strategies and edge-feature integration to enhance predictive accuracy. 

### Highlights:
- **MPNN** achieved the best performance with a test accuracy of **83.7%** and an F1 score of **87.9%**.
- Integration of hierarchical pooling (TopKPooling) improved performance and scalability.
- This framework demonstrates the potential of GNNs in drug discovery.

---

## Dataset

The dataset used for this project was sourced from **MoleculeNet**, containing 41,127 molecules labeled by their HIV inhibition activity:
- **Training Set**: 37,128 molecules (balanced via oversampling and downsampling techniques).
- **Test Set**: 3,999 molecules.

Each molecule is represented as a graph:
- **Nodes**: Atomic features (e.g., atomic number, hybridization state, aromaticity).
- **Edges**: Bond-level features (e.g., bond type, part of a ring).

---

## Methodology

### 1. **GCN**:
- Explored global pooling strategies: **mean**, **sum**, and **max pooling**.
- Introduced hierarchical pooling with **TopKPooling** for multi-level structural information retention.

### 2. **MPNN**:
- Incorporated **edge features** in message passing for enhanced expressiveness.
- Conducted grid search to optimize hyperparameters:
  - **Learning Rate**: [0.01, 0.005]
  - **Embedding Size**: [16, 32, 64]
  - **Pooling Ratio**: [0.4, 0.5, 0.6]
  - **Dropout Rate**: [0, 0.2]

---

## Results

| Model        | Test Accuracy | Test F1 Score |
|--------------|---------------|----------------|
| **GCN (Sum)** | 70.2%         | 78.9%          |
| **GCN (TopKPooling)** | 76.6% | 83.3%          |
| **MPNN**      | **83.7%**     | **87.9%**      |

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/annadu03/583final-project.git
   cd 583final-project
2. Install dependencies
pip install -r requirements.txt

3.The code to reproduce the work is in the final project
