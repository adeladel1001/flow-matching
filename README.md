# 🧠 Flow Matching for Improved Latent Generative Modeling

This project explores **Flow Matching**, a recent generative modeling approach, to improve the quality of samples generated from a **Variational Autoencoder (VAE)**.

Instead of relying on direct Gaussian sampling in the latent space, Flow Matching learns a **continuous transport dynamics** that maps noise to more realistic latent representations.

---

## 🚀 Project Overview

Variational Autoencoders often suffer from a mismatch between the assumed prior distribution:

\[
z \sim \mathcal{N}(0, I)
\]

and the true latent distribution learned by the encoder.

To address this, we integrate **Flow Matching** to learn a velocity field:

\[
v_\theta(z, t)
\]

that progressively transports samples from a simple noise distribution toward the true latent manifold.

This results in:

- More plausible latent codes  
- Higher-quality decoded samples  
- Improved stability compared to naive sampling  

---

## ✨ Key Features

- Implementation of a **VAE baseline** for image generation  
- Flow Matching model trained to approximate latent transport  
- Comparison between:
  - Standard Gaussian latent sampling  
  - Flow-Matching-based sampling  
- Experiments with different model capacities:
  - **FM-small**
  - **FM-base**
  - **FM-large**

---

## 🏗️ Architecture

### Variational Autoencoder (VAE)

- Encoder outputs mean and variance of latent variables  
- Decoder reconstructs images from latent vectors  

### Flow Matching Module

- Learns a continuous velocity field  
- Transforms an initial noise sample \(z_0\) into a realistic latent sample \(z_1\)

---

## 📊 Results

Our experiments show that:

- **Flow Matching produces sharper and more coherent generations**
- Model capacity strongly impacts sample quality:
  - Smaller networks struggle to approximate the velocity field  
  - Larger models generate more stable and realistic outputs  

Flow Matching improves latent sampling beyond classical Gaussian assumptions.
