# COVID-image-classification
COVID-image-classification

## Modeling

Baseline model: This model has two convolutional layers with 32 and 64 filters respectively, followed by a dense layer with 16 units and a sigmoid output layer. It uses a batch size of 64 and an early stopping callback with a minimum delta of 1e-2 and patience of 5. The loss function is 'binary_crossentropy'.

Model 1: This model is similar to the baseline model, but has an additional MaxPooling2D layer after the second convolutional layer, and a dense layer with 64 units before the output layer. It uses a batch size of 32 and trains for 10 epochs with no early stopping.

Model 2: This model is also similar to the baseline model, but has L2 regularization with a weight of 0.01 on the weights of the second and third convolutional layers, and the dense layer before the output layer. It uses a batch size of 32 and trains for 10 epochs with no early stopping. Additionally, it tracks precision and recall as additional metrics.

Model 3 (final model): This model has a more complex architecture, with four convolutional layers, each with 32 or 64 filters, followed by two dense layers with 256 units each, and a sigmoid output layer. It uses a batch size of 32 and trains for 20 epochs with no early stopping. The loss function is 'binary_crossentropy' and the optimizer is 'Adam'.
