# Feature Engineering vs Model Complexity: A Linear Separability Experiment

This repository demonstrates the fundamental relationship between feature engineering and model complexity in machine learning through the classic odd/even number classification problem. The experiment explores how proper data representation can make simple algorithms outperform complex models, emphasizing the critical importance of feature engineering in machine learning.

## 🎯 Objective

To explore the relationship between feature engineering and model complexity while understanding how important feature engineering can be, specifically:

- Understanding when simple perceptrons succeed vs. fail
- Demonstrating that feature engineering often trumps algorithmic complexity
- Illustrating the concept of linear separability through practical examples
- Showing how the same problem can be impossible or trivial based on data representation

## 📚 Background

The perceptron is one of the foundational algorithms in machine learning, capable of classifying binary classes from linearly separable datasets. However, not all problems are inherently linearly separable, which leads to interesting insights about data representation and feature engineering.

## 🧪 Experiments

### 1. Raw Numbers Approach

- **Input**: Raw numbers [0, 1, 2, 3, 4, 5, ...]
- **Result**: ~50% accuracy (equivalent to random guessing)
- **Analysis**: The alternating pattern of odd/even numbers cannot be separated by any single threshold

### 2. ASCII Representation

- **Input**: ASCII values of the last digit [48, 49, 50, 51, ...]
- **Result**: ~50% accuracy
- **Analysis**: ASCII encoding doesn't preserve the linear separability needed for classification

### 3. One-Hot Encoding (Success!)

- **Input**: One-hot encoded last digit (10-dimensional vectors)
- **Result**: 100% accuracy
- **Analysis**: Creates linearly separable features that allow perfect classification

## 🏗️ Implementation

The repository includes from-scratch implementations of:

### Perceptron Class

```python
class Perceptron:
    def __init__(self, N, alpha=0.1)
    def step(self, x)
    def fit(self, X, Y, epochs=1000)
    def predict(self, X, addBias=True)
```

### Multi-Layer Perceptron (MLP)

```python
class MLP:
    def __init__(self, input_size, hidden_size, output_size)
    def sigmoid(self, x)
    def softmax(self, x)
    def forward(self, X)
    def backward(self, X, y, output, learning_rate)
    def train(self, X, y, epochs, learning_rate)
    def predict(self, X)
```

## 📊 Results Summary

| Approach         | Input Representation  | Accuracy | Linearly Separable? |
| ---------------- | --------------------- | -------- | ------------------- |
| Raw Numbers      | [0, 1, 2, 3, ...]     | ~50%     | ❌ No               |
| ASCII Values     | [48, 49, 50, 51, ...] | ~50%     | ❌ No               |
| One-Hot Encoding | 10D binary vectors    | 100%     | ✅ Yes              |

## 🔑 Key Insights

1. **Feature Engineering > Model Complexity**: Proper features make simple algorithms work better than complex algorithms with poor features
2. **Linear Separability is the Key**: The same problem can be impossible or trivial depending on data representation
3. **Understanding Your Data Matters**: Knowing the mathematical properties of your input representation is crucial
4. **The Classic XOR Problem**: This experiment demonstrates a fundamental example of when linear classifiers fail
5. **Simplicity Through Smart Representation**: Sometimes the best solution is the simplest one, given the right features

## 🚀 Getting Started

### Prerequisites

- Python 3.x
- NumPy
- Matplotlib

### Running the Notebook

```bash
git clone <repository-url>
cd perceptron
jupyter notebook perceptron_scratch_odd_or_even.ipynb
```

## 📁 File Structure

```text
├── perceptron_scratch_odd_or_even.ipynb  # Main experiment notebook
├── README.md                             # This file
└── .gitignore                           # Git ignore file
```

## 🔍 Detailed Analysis

The notebook provides:

- Step-by-step implementation of algorithms from scratch
- Comprehensive visualizations showing why certain approaches fail
- Accuracy measurements and performance analysis
- Clear explanations of the feature engineering vs. complexity trade-off
- Practical demonstrations of linear separability concepts

## 🎓 Learning Outcomes

After working through this repository, you will understand:

- Why feature engineering is often more important than choosing complex algorithms
- How perceptrons make decisions using linear thresholds
- The fundamental concept of linear separability and its practical implications
- When to choose simple vs. complex algorithms based on your data representation
- The relationship between data representation and model performance
- How the same problem can have drastically different solution complexities

## 🤝 Contributing

Feel free to:

- Open issues for questions or suggestions
- Submit pull requests for improvements
- Share your own experiments with different representations

## 📜 License

This project is open source and available under the [MIT License](LICENSE).

---

**Key Takeaway**: This experiment proves that smart feature engineering can make the difference between an impossible problem and a trivial one. Sometimes the best algorithmic innovation is choosing the right representation of your data!
