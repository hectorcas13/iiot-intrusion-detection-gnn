# IIoT Intrusion Detection with Graph Neural Networks

This repository contains an Industrial Internet of Things (IIoT) intrusion-detection research project using the CIC IIoT Dataset 2025. It compares classical tabular classification models, graph-analysis baselines, and richer graph neural network (GNN) designs for benign-versus-attack detection.

## Research Question

Does using a knowledge graph with a graph neural network detect attacks on IIoT traffic better than standard models that do not use graphs?

## Project Workflow

1. Analyze benign IIoT traffic.
2. Analyze attack traffic.
3. Compare benign and attack behavior.
4. Evaluate classical tabular classification baselines.
5. Construct device-to-behavior-state graph baselines.
6. Build a richer heterogeneous graph with device, state, IP, port, protocol, and temporal nodes.
7. Compare GCN, GraphSAGE, GAT, and R-GCN-like architectures.

## Main Notebooks

- `notebooks/CIC IIoT dataset 2025_Benign data.ipynb`
- `notebooks/CIC IIoT dataset 2025_attack data.ipynb`
- `notebooks/Benign vs Attack.ipynb`
- `notebooks/Baseline Models and GNN Roadmap.ipynb`
- `notebooks/Rich Graph GNN Experiments.ipynb`

## Methods

Classical models:

- Logistic Regression
- Naive Bayes
- Linear Discriminant Analysis (LDA)
- Quadratic Discriminant Analysis (QDA)
- k-Nearest Neighbors (k-NN)

Graph and GNN methods:

- Benign novelty graph
- Dual-class affinity graph
- State co-occurrence graph
- Graph Convolutional Network (GCN)
- GraphSAGE
- Graph Attention Network (GAT)
- R-GCN-like relation-aware architecture

## Graph Representations

The baseline graph-analysis methods use a simpler device-to-behavior-state representation:

```text
device -> behavior-state
```

The richer graph extends this into a heterogeneous knowledge-graph-style representation:

```text
device -> behavior-state
device -> IP
device -> port
device -> protocol
device -> time
time_bucket -> next_time_bucket
```

## Dataset

The original CIC IIoT Dataset 2025 files are not stored in this repository because of their size and redistribution considerations. Download the dataset from the official source:

- https://www.unb.ca/cic/datasets/iiot-dataset-2025.html

Files used in this project include:

- `benign_samples_1sec.csv`
- `attack_samples_1sec.csv`

## Software

- Python
- Jupyter Notebook
- pandas and NumPy
- scikit-learn
- NetworkX
- Matplotlib
- PyTorch

## Validation Note

Very high rich-graph GNN performance under a random window-level split should be interpreted cautiously. Future work should test time-based, device-based, and attack-family holdout splits to evaluate generalization and possible indirect leakage.

## Code and Data Availability

This repository provides the notebooks and research workflow. The CIC IIoT Dataset 2025 is not redistributed; readers should obtain it from the official dataset source.
