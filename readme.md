# An Enhancement in Psychiatric Disorder Detection: A Roadmap in Brain-Computer Interface (BCI) using Graph Neural Networks (GNN)

## Overview

This project aims to enhance the detection of psychiatric disorders using Graph Neural Networks (GNN) on EEG data. Traditional machine learning models like LSTM and CNN have shown poor performance in multi-class classification tasks in this domain. By employing GNN, this project achieves a significant improvement in accuracy.

## Dataset

The dataset used for this project is the EEG data from Kaggle given my Mentor Dr. Sriparna Saha https://www.kaggle.com/datasets/shashwatwork/eeg-psychiatric-disorders-dataset . It includes various features extracted from EEG signals and corresponding labels for different psychiatric disorders.

## Key Results

- Overall classification accuracy of **92%** (±5%) across seven categories of psychiatric disorders.

### Training Progress

The model was trained for 200 epochs with the following notable results:

- **Epoch 10:** Loss: 1.7307, Accuracy: 0.3608
- **Epoch 50:** Loss: 1.2313, Accuracy: 0.5471
- **Epoch 200:** Loss: 0.2799, Accuracy: 0.9196

### Classification Report for Main Disorders

The classification report for the main disorders includes:

| Disorder                           | Precision | Recall   | F1-Score | Support |
| ---------------------------------- | --------- | -------- | -------- | ------- |
| Addictive disorder                 | 0.82      | 0.98     | 0.89     | 186     |
| Anxiety disorder                   | 0.94      | 0.93     | 0.93     | 107     |
| Healthy control                    | 0.90      | 0.94     | 0.92     | 95      |
| Mood disorder                      | 0.97      | 0.94     | 0.96     | 266     |
| Obsessive compulsive disorder      | 0.87      | 0.87     | 0.87     | 46      |
| Schizophrenia                      | 0.98      | 0.97     | 0.98     | 117     |
| Trauma and stress-related disorder | 0.95      | 0.73     | 0.83     | 128     |
| **Accuracy**                       | **0.92**  |          |          | 945     |
| **Macro Avg**                      | **0.92**  | **0.91** | **0.91** | 945     |
| **Weighted Avg**                   | **0.92**  | **0.92** | **0.92** | 945     |

## Installation

1. Clone the repository:
   git clone https://github.com/sarman12/Graph-neural-network.git
   cd your_repository

2. Install the following dependencies:
   pip install torch torch_geometric pandas seaborn matplotlib scikit-learn

3. Run the file:
   python gnn_model.py
