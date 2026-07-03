# link


# Summary 

In the context of neural networks, particularly in architectures like **Convolutional Neural Networks (CNNs)**, **Flatten** is an operation that **transforms a multi-dimensional array (or tensor) into a one-dimensional (1D) array (or vector)**.

Its core purpose is to **prepare the output of convolutional and pooling layers to be fed as input into fully connected (dense) layers**.

- **Input:** Typically takes the output of a convolutional or pooling layer, which is usually a 3D (height x width x channels) or even 4D (batch size x height x width x channels) tensor.
- **Process:** It rearranges all the elements from the multi-dimensional array into a single, long sequence. For example, if you have a 3x3x5 tensor, flattening it would result in a 1D vector of 45 elements (3 * 3 * 5).
- **Why it's needed:** Fully connected layers expect a 1D vector as input. They don't inherently understand the spatial relationships (height, width, channels) that convolutional layers process. Flattening preserves the information while converting it into the required format for the dense layers to perform final classification or regression.

**In essence, Flatten is like taking a stack of photos (multi-dimensional) and arranging them all in a single, long line (1D vector) so you can feed them one by one into a final processing unit that doesn't care about their original picture-like layout, just their individual pixel values.

# Related Concepts

*  [[fully connected layer]]
