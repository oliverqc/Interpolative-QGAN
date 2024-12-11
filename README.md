# A quantum animation program
The goal of this project was to increase the emotional value of art by optimizing emotional space using the QGAN model. The QGAN takes image input data and generates an animated sequence. 

<img src="https://github.com/user-attachments/assets/fe9609c5-6cb8-4601-ad6e-7c70e04fcb3c" width="700" height="600"/>

### Watch my video walk-through
https://youtu.be/XFa2MbDxFoA

### Structure 
This algorithm was built using Pytorch and Qiskit. It utilizes a hybrid-structure with a QNN for the generator and a classical discriminator. There structure is generally:

```python
def build_quantum_generator():
    set number of qubits
    create quantum circuit with qubits
    for each qubit:
        initialize with y gate

    apply hadamard to all qubits
    create ansatz circuit using EfficientSU2
    compose ansatz into main circuit
```

```python
def build_discriminator():
    initialize discriminator class
    define input shape
    create convolutional blocks:
        (n) number of conv blocks:
            conv layer
            activation layer
            dropout layer

    calculate input size for fully connected layer
    create fully connected layers:
        flatten layer
        dropout layer
        linear layer
        activation layer

    define forward pass

create the discriminator instance
```
After applying our unitary operator to the trained parameters of the generator and discriminator we can produce our in-between images. 

<img width="698" alt="Screenshot 2024-12-10 at 10 03 18 PM" src="https://github.com/user-attachments/assets/a4deb9fb-b8e8-4c0d-8804-7c4c21255703">

### Sources 
Nielsen, Michael A., and Isaac L. Chuang. Quantum Computation and
Quantum Information. Cambridge University Press, 2010.

Kim, Leeseok, et al. "Hamiltonian Quantum Generative Adversarial Networks." arXiv, 4 Nov. 2022, https://doi.org/10.48550/arXiv.2211.02584.

Shu, Runqiu, et al. "Variational Quantum Circuits Enhanced Generative Adversarial Network." arXiv, 2 Feb. 2024, https://doi.org/10.48550/arXiv.2402.01791.


