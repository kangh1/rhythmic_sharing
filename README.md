## Introduction
_**Disclaimer: This introduction is adapted from the doctoral disseration written by Hoony Kang.**_

Artificial neural networks train by finding optimal weights, which are the strengths of connections between neuronal nodes. These optimal values are found by minimizing the error between the neural network’s output and what we know should be the true output for given inputs used during training. However, much of the real world is governed by non-stationary dynamics, wherein the underlying statistics of the dynamics drift in time in an arbitrary way. When an artificial neural network (ANN) is trained with a loss function that is uninformed of the different probability spaces present in the training data (e.g., through contextual tokens), the ANN will treat the entire data as if it had come from one stationary probability distribution—in effect, as one ‘event’—and cannot differentiate between the different dynamics without instruction. While this outstanding problem has motivated the study of adaptive dynamical networks, where biological learning rules influence the network weights, the monotonic nature of these rules (that is, where weights increase or decrease monotonically to converge to some local minimum of the loss), including backpropagation, poses yet another problem: the loss of stability.

Yet the living neural networks of brains can rapidly infer contextual changes in real-time, adapt their behavior in accordance with this new environment, and even induce how the organism should act in an unencountered environment. Here, we introduce a learning paradigm that associates learning with the coordination of oscillations of link strength. The paradigm is inspired by the physics of oscillatory rhythms of the mechanical structures that support synapses. It yields rapid adaptation and learning in neural networks while maintaining robustness. Links can rapidly change their coordination of oscillations, endowing the network with the ability to sense subtle context changes in an unsupervised manner. In other words, the network generates the missing contextual tokens required to perform as a generalist AI architecture, capable of predicting dynamics in multiple contexts. Furthermore, the oscillations themselves allow the network to extrapolate dynamics to never-seen-before contexts. This oscillation-based learning paradigm provides a starting point for novel models of learning and cognition. Because it is agnostic to the specific details of the neural network architecture, this paradigm also opens the door for introducing rapid adaptation and learning capabilities into leading AI models.

This model utilizes dynamical systems theory and algebraic topology (homotopy) theory. Specifically, the model may be thought of as involving dynamic interactions between a network of 0-simplices (nodes) and a network of 1-simplices (links), each evolving as a unique dynamical system. By simply needing to specify the mean phase variables $(R, \langle \Phi\rangle)$ to steer the network into a desired basin of attraction, the dimension required to specify the control object is effectively reduced from $\mathbb{R}^{N_n}$ to $\mathbb{R}^2$.

## What is included in this repository

- **thomas.csv** : 	CSV file of nonstationary data of Thomas system. This file is used in the example Python notebook that runs the algorithm (see below).
- **thomas_periodic_orbit.csv** : CSV file of the periodic orbit of the Thomas system, corresponding to b = 0.29 (see sect.4.1.1 in the manuscript).
- **rhythmic_sharing_example.ipynb** : Jupyter notebook of the algorithm using nonstationary data from the Thomas system, as used in the manuscript. Prediction of stationary states is not shown in the notebook, as that is up to the user to define which $\langle \Phi\rangle$ to freeze. Instead, an output trajectory showing the network continuously hopping through various individual attractors as $\langle \Phi\rangle$ evolves linearly is shown in the notebook output.
- **thomas_data_generate.nb** : Mathematica notebook used to generate data of Thomas system.
  


## Compatibility
Python 3.9.13

Mathematica 13.2.0.0 (only used for sample data generation; not necessary to run for the algorithm)

No GPU is needed. For the Thomas system, runtime is on the order of seconds if executing the code locally on your laptop.

## Intellectual property notice
The code available on this page is based on the algorithm filed under U.S. Provisional Application No. 63/716,102.
