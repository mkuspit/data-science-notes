# Machine Learning

## Supervised Learning



- Classification (states)

- Regression (numeric values)

Data split:

- Train set - training models (parameters)

- Cross-validation set - picking the best model (modeling technique, hyper-parameters)
- Test set - final check



### Classification

|                | Guessed `POSITIVE` | Guessed `NEGATIVE` |
| -------------- | ------------------ | ------------------ |
| **`POSITIVE`** | TRUE POSITIVE      | FALSE NEGATIVE     |
| **`NEGATIVE`** | FALSE POSITIVE     | TRUE NEGATIVE      |

### Errors:

- False Positive - Type 1 error
- False Negative - Type 2 error



#### Performance Metrics

- $Accuracy = \frac{TP + TN}{ TP + TN + FP + FN}$

- $Recall = \frac{TP}{TP + FN}$ - sensitivity, avoid FN, TP rate

- $Precision = \frac{TP}{TP + FP}$ - avoid FP

- $Specificity = \frac{TN}{TN + FP}$ - TN rate

- $F_1 Score = 2 \frac{Precision Recall}{Precision + Recall}$ - harmonic recall

- $F_\beta Score = (1 + \beta^2) \frac{Precision * Recall}{\beta^2 * Precision + Recall}$

- ROC Curve (Receiver Operating Characteristic)
    - x axis - 1 - Spicificity
    - y axis - Recall
    - Higher area under curve means better model
        - area = 1 -> perfect model
        - area = 0.5 -> random





### Regression



#### Performance Metrics



- Mean Absolute Error: $MAE = \frac{1}{n} \sum_{i=1}^{n}(|\hat{y}_{i} - y_{i}|)$

- Mean Square Error: $MSE = \frac{1}{2n} \sum_{i=1}^{n}(\hat{y}_{i} - y_{i})^2$

- $R^2 = \frac{SS_{reg}}{SS_{tot}} = \sum_{i}\frac{(\hat{y}_i-\bar{y})^2}{(y_i-\bar{y})^2}$  

