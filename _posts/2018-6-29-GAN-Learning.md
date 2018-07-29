---
layout: post
title: GAN Learning
---

Hello welcome to my third post! Today I want to talk about GAN Learning! Many ideas below are borrowed from [1].

Generative adversarial networks(GANs) are an example of generative models.

What is generative models?
- Any models that takes a training set, consisting of samples drawn from a distribution $p_{data}$, and learns to represent an estimate of that distribution $p_{model}$. The model may estimate $p_{model}$ explicitly or only able to generate samples from $p_{model}$ or can do both. GANs focus on sample generation.

## Research value of generative modeling
1. Our ability to represent and manipulate high-dimensional probability distributions could be tested by training and sampling from generative models.
2. Generative models can be incorporated into reinforcement learning in several ways.
3. Generative models can be trained with missing data and are able to provide predictions on inputs that are missing data. `Semi-supervised learning` is a very good example.
4. Generative models, GANs in particular, enable machine learning to work with multi-model outputs. Many traditional methods for model training, e.g. using mean squared error between model's predicted output and ground truth, choose to impose a single best output averaging many slightly different correct answers. Instead, GANs are able to understand that there are multiple correct answers.
5. Many tasks intrinsically require realistic generation of samples from some distribution, e.g. Single image super-resolution, Image-to-image translation applications, Art work etc.

## Mechanism of generative models
### Maximum likelihood estimation
The principle of maximum likelihood is to choose the parameters for the model that maximize the likelihood of the training data.
$\theta_* = \arg\max_{\theta} \pred_{i=1}^mp_{model}(x^{(i)};\theta)$
$\theta_* = \arg\max_{\theta} \sum_{i=1}^m logp_{model}(x^{(i)};\theta)$
**We can also think of maximum likelihood estimation as minimizing the KL divergence between the data generating distribution and the model:**
$\theta_* = \arg\min_{\theta}D_{KL}(p_{data}(x)||p_{model}(x;\theta))$
However, in practice, we do not have access to $p_{data}$ itself, we only use a training set consisting of m samples from $p_{data}$ to define $\hat{p_{data}}$. Minimizing the KL divergence between $\hat{p_{data}}$ and $p_{model}$ is exactly equivalent to maximizing the log-likelihood of the training set.

### A taxonomy of deep generative models

TODO: here need add a figure

Three most popular approaches to generative modeling: FVBNs, GANs and variational autoencoders.

#### Tractable explicit models
There are currently two popular approaches to tractable explicit density models: **fully visible belief networks** and **nonlinear independent components analysis**.
- Fully visible belief networks(FVBN)
FVBNs are models that use the chain rule of probability to decompose a probability distribution over an n-dimensional vector x into a product of one-dimensional probability distributions.
$p_{model}(x) = \pred_{i=1}^np_{model}(x_i|x_1,...,x_{i-1})$
Drawback: Samples must be generated one entry at a time: first $x_1$, then $x_2$, etc., so the cost of generating a sample is O(n).
Compared to GANs: GANs generate all of x in parallel, yielding greater generation speed.

- Nonlinear independent components analysis
The core concept is defining continuous nonlinear transformations between two different spaces. There is a vector of latent variables z and a continuous differentiable invertible transformation g such that g(z) yields a sample from the model in x space, then
$p_x(x) = p_z(g^{-1}(x))|det(\frac{\partial g^{-1}(x)}{\partial x})|$ [2]
If $p_z$ and the determinant of the Jacobian of $g^{-1}$ are tractable, the density $p_x$ is tractable.
Drawback: They impose restrictions on the choice of the function g. In particular, the invertibility requirement means that the latent variables z must have the same dimensionality as x.
Compared to GANs: GANs were designed to impose very few requirements on g, and, in particular, admit the use of z with larger dimension than x.

#### Explicit models requiring approximation
To avoid some of the disadvantages imposed by the design of requirements of models with tractable density functions, other explicit models require the use of approximations to maximize the likelihood. These fall roughly into two categories: those using **deterministic approximations**, which almost always means variational methods, and those using **stochastic approximations**, meaning Markov chain Monte Carlo(MCMC) methods.

- Variational approximations
Variational methods define a lower bound:
$L(x;\theta) \pm logp_{model}(x;\theta)$
It is possible to define an L that is computationally tractable even when the loglikelihood is not. Learning can be viewed as maximizing L with respect to $\theta$.
Most popular approach: Variational Autoencoder(VAE)
Drawback: When too weak of an approximate posterior distribution or too weak of a prior distribution is used, even with a perfect optimization algorithm and infinite training data, the gap between L and the true likelihood can result in $p_{model}$ learning something other than the true $p_{data}$.
Compared to GANs: GANs were designed to be unbiased with a large enough model and infinite data. Variational methods often obtain very good likelihood, but are regarded as producing lower quality samples.
Compared to FVBNs, VAEs are more difficult to optimize.

- Markov chain approximations
A Markov chain is a process for generating samples by repeatedly drawing a sample $x'~q(x'|x)$. Markov chain methods can sometimes guarantee that x will eventually converge to a sample from $p_{model}(x)$.
Drawback:
Compared to GANs: GANs were designed to avoid using Markov chains.

Deep Boltzmann machines make use of both types of approximation.

#### Implicit density models

To be continued...


























## Comparison of GAN and others







[1] NIPS 2016 Tutorial: Generative Adversarial Networks
[2] https://en.wikipedia.org/wiki/Integration_by_substitution#Application_in_probability
