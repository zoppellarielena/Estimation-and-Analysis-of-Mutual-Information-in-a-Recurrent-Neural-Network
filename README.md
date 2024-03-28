# Estimation and Analysis of Mutual Information in a Recurrent Neural Network

Mutual information, a fundamental concept in information theory, quantifies the amount of information one random variable contains about another. Accurate estimation of mutual information is essential in various machine learning and statistical tasks. This project delves into methods for estimating mutual information between the layers of a recurrent neural networks trained for a cognitive task. Specifically, we analyzed a pre-trained recurrent neural network through the lens of information content.

The dataset employed in this study corresponds to the GO task described by Yang et al. (2019)[^1]. In this task, a stimulus at a specific direction is provided as input over a duration of 90 seconds. The network is trained to respond in the same direction. The recurrent neural network consists of a single hidden layer with $N_{rec} = 256$ neurons, and training is conducted using 200 input signals. Each signal is represented by a Gaussian distribution ranging from 0 to 32 degrees, centered at the stimulus direction during active periods, or noise during inactive periods.

The estimation methods utilized include:

* **Binning Estimator** (discrete), which is able to return satifying results for a sufficiently small number of bins ($nbins = 2$)
* **Gaussian estimator**, in particular we have adapted the method by Kolchinsky and Tracey[^2] to handle the hidden layer, which can be viewed as homoscedastic mixtures of Gaussians given by $T = h + \epsilon$, where $\epsilon \sim \mathcal{N}(0,\sigma^2 \mathbb{1})$.
* **Kraskov estimator**

Furthermore, we conduct an analysis on the mutual information carried by individual neurons, revealing distinct behaviors among them. Notably, active neurons do not remain active throughout the expected duration; instead, they reach individual peaks at random moments, which vary between neurons.

Lastly, we replicate all experiments on a different network trained to perform the same task using reservoir computing.

This project, developed between January and March 2024 as part of the exam for the *Information Theory and Inference* course at the University of Padova, during the academic year 2023-2024, was undertaken by the team consisting of:
* Golan Rodrigo
* Zoppellari Elena

[^1]: Yang, G.R., Joglekar, M.R., Song, H.F. et al. Task representations in neural networks trained to perform many cognitive tasks. Nat Neurosci 22, 297–306 (2019)
[^2]: https://arxiv.org/abs/1706.02419
