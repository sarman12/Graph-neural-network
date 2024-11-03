This project provides a graph-based structure for representing EEG data, leveraging node features, edge indices, and edge attributes. The graphs are constructed to enable analysis using Graph Neural Networks (GNNs) such as GCN, GAT, and GraphSAGE.

## Graph Structure Overview

For each subject, the EEG data is structured as a graph with nodes, edges, and features. Below is the graph information for one subject:

- **Number of Nodes:** 19
- **Number of Edges:** 171
- **Node Feature Shape:** [19, 6]
- **Edge Index Shape:** [2, 171]
- **Edge Attribute Shape:** [171, 6]
- **Graph Label:** 2

### Detailed Components

- **Nodes** represent EEG channels, with each node containing 6 features corresponding to specific frequency bands.
- **Edges** connect pairs of EEG channels and capture inter-channel coherence as edge attributes.
- **Edge Attributes** have a shape of `[171, 6]`, with each edge attribute containing 6 values, representing coherence values across bands.

## Models

This project includes three GNN models for graph classification tasks:
1. **GCN (Graph Convolutional Network)**
2. **GAT (Graph Attention Network)**
3. **GraphSAGE**

## Results

### GCN Model

- **Best Train Accuracy:** 68.48%
- **Best Test Accuracy:** 52.27%
- **Classification Report (Train)**:
  
  | Disorder                        | Precision | Recall | F1-score |
  |---------------------------------|-----------|--------|----------|
  | Addictive disorder              | 0.51      | 0.73   | 0.60     |
  | Anxiety disorder                | 0.87      | 0.51   | 0.64     |
  | Healthy control                 | 0.68      | 0.65   | 0.67     |
  | Mood disorder                   | 0.42      | 0.74   | 0.53     |
  | Obsessive compulsive disorder   | 0.96      | 0.35   | 0.51     |
  | Schizophrenia                   | 0.62      | 0.67   | 0.64     |
  | Trauma and stress related disorder | 0.83   | 0.65   | 0.73     |
  
  **Overall Accuracy (Train):** 61%

- **Classification Report (Test)**:
  
  | Disorder                        | Precision | Recall | F1-score |
  |---------------------------------|-----------|--------|----------|
  | Addictive disorder              | 0.28      | 0.52   | 0.36     |
  | Anxiety disorder                | 0.70      | 0.47   | 0.56     |
  | Healthy control                 | 0.53      | 0.58   | 0.55     |
  | Mood disorder                   | 0.24      | 0.41   | 0.30     |
  | Obsessive compulsive disorder   | 1.00      | 0.22   | 0.36     |
  | Schizophrenia                   | 0.52      | 0.55   | 0.53     |
  | Trauma and stress related disorder | 0.71   | 0.42   | 0.53     |
  
  **Overall Accuracy (Test):** 45%

### GraphSAGE Model

- **Best Train Accuracy:** 94.16%
- **Best Test Accuracy:** 71.31%
- **Classification Report (Train)**:

  | Disorder                        | Precision | Recall | F1-score |
  |---------------------------------|-----------|--------|----------|
  | Addictive disorder              | 0.87      | 0.94   | 0.90     |
  | Anxiety disorder                | 0.94      | 0.85   | 0.89     |
  | Healthy control                 | 0.83      | 0.95   | 0.88     |
  | Mood disorder                   | 0.93      | 0.85   | 0.89     |
  | Obsessive compulsive disorder   | 0.97      | 0.93   | 0.95     |
  | Schizophrenia                   | 0.92      | 0.95   | 0.94     |
  | Trauma and stress related disorder | 0.95   | 0.92   | 0.93     |
  
  **Overall Accuracy (Train):** 91%

- **Classification Report (Test)**:

  | Disorder                        | Precision | Recall | F1-score |
  |---------------------------------|-----------|--------|----------|
  | Addictive disorder              | 0.64      | 0.68   | 0.66     |
  | Anxiety disorder                | 0.73      | 0.68   | 0.71     |
  | Healthy control                 | 0.63      | 0.78   | 0.70     |
  | Mood disorder                   | 0.48      | 0.34   | 0.40     |
  | Obsessive compulsive disorder   | 0.88      | 0.83   | 0.86     |
  | Schizophrenia                   | 0.70      | 0.83   | 0.76     |
  | Trauma and stress related disorder | 0.72   | 0.64   | 0.68     |
  
  **Overall Accuracy (Test):** 69%

### GIN Model

- **Best Train Accuracy:** 95.55%
- **Best Test Accuracy:** 71.02%
- **Classification Report (Train)**:
  *(Please include train classification report details if available)*

- **Classification Report (Test)**:
  *(Please include test classification report details if available)*

## Early Stopping and Model Selection

Each model utilized early stopping to prevent overfitting, and the final test accuracy was recorded after early stopping was triggered.

## Conclusion

GraphSAGE performed the best on this EEG classification task, achieving a test accuracy of 71.31% and strong F1-scores across various psychiatric disorder categories. This suggests that GraphSAGE’s sampling-based approach may be more effective for this EEG dataset compared to GCN and GIN.

## Future Work

1. **Hyperparameter Tuning**: Explore different learning rates, batch sizes, and hidden dimensions.
2. **Advanced Architectures**: Experiment with more advanced GNN architectures or attention-based models.
3. **Feature Engineering**: Further explore feature extraction from EEG signals for improved classification.

## How to Run

1. Clone the repository.
2. Install required dependencies.
3. Execute the training script for the desired model.
4. Monitor performance metrics and visualize classification reports for each model.

## Dependencies

- PyTorch
- PyTorch Geometric
- scikit-learn
- numpy
- pandas

## License

This project is licensed under the MIT License. See the `LICENSE` file for more information.