# Back-Propagation Neural Network: Cross-Entropy Error and Weight Decay

CS345 - Applied Artificial Intelligence
Student: Daragosa, Charles Benedict B.

## Modifications

The back-propagation program was modified with two switches, passed to `Train()`:

1. **Cross-entropy error** (`useCrossEntropy`): the output-node signal is `(t - o)` instead of `(t - o) * o * (1 - o)`, and the reported error is the average cross-entropy, `-Σ t·ln(o)`.
2. **Weight decay / L2 regularization** (`weightDecay`): each weight update subtracts `lambda * w`. Biases are not decayed. `0.0` turns it off.

## How to run

Open the project in Visual Studio and press **Ctrl+F5**, or from the project folder run:

```
dotnet run
```

The program trains two networks in one execution, using the same data, initial weights and hyperparameters (1000 epochs, learning rate 0.05, momentum 0.01):

| Run | Configuration | Train accuracy | Test accuracy |
|---|---|---|---|
| 1 | Cross-entropy, no weight decay | 0.9913 | 0.9700 |
| 2 | Cross-entropy with weight decay (lambda = 0.0001) | 0.9575 | 0.9500 |
