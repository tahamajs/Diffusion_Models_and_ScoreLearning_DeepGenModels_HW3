# ELBO-KL-Diffusion-ScoreBased-DGM-HW3

## 📌 Table of Contents

- [Introduction](#introduction)
- [Course Information](#course-information)
- [Assignment Details](#assignment-details)
- [Sections Overview](#sections-overview)
  - [Diffusion Models](#diffusion-models)
  - [Score-Based Models](#score-based-models)
- [Implementation Details](#implementation-details)
- [Mathematical Derivations](#mathematical-derivations)
- [Training and Experimentation](#training-and-experimentation)
- [Submission Guidelines](#submission-guidelines)
- [Academic Integrity Policy](#academic-integrity-policy)
- [License](#license)

---

## 📝 Introduction

This repository contains **Homework 3** for the **Deep Generative Models** course at the **University of Tehran**. This assignment covers **cutting-edge generative models**, including:

- **Diffusion-based models** (DDPM, DDIM)
- **Score-based generative models**
- **Langevin dynamics for probabilistic modeling**
- **FID evaluation and training efficiency comparisons**

This assignment provides **both theoretical and practical** components, allowing students to explore **modern generative models** and implement them efficiently in Python.

---

## 🎓 Course Information

- **University**: University of Tehran
- **Department**: Electrical and Computer Engineering
- **Course**: Deep Generative Models
- **Instructor**: Dr. Mostafa Tavasoli
- **Term**: Fall 1403

---

## 🏆 Assignment Details

This homework consists of **two major sections**:

### 🔹 **1. Diffusion Models (DDPM & DDIM)**:

- **Understanding Diffusion Models** (Forward and Backward Processes)
- **Implementing and comparing DDPM & DDIM**
- **Training on the Sprites dataset**
- **Computing FID for evaluation**

### 🔹 **2. Score-Based Generative Models**:

- **Mathematical derivation of score functions**
- **Implementing Langevin dynamics for sampling**
- **Comparing different noise perturbation strategies**
- **Training and evaluating score-based models**

---

## 📂 Sections Overview

### 🔥 **Diffusion Models**

Diffusion models are a **powerful class of generative models** that add noise to data in a **forward process** and then learn to reverse this corruption through a **backward process**.

#### ✅ **Tasks:**

1. **Mathematical Properties of Diffusion Models**:

   - Prove why diffusion does not need **iterative noise addition**.
   - Explain why **Gaussian assumptions** hold in the reverse process.
   - Analyze the loss function of **DDPM** and why some terms are omitted.
2. **Implementing DDPM & DDIM**:

   - Implement the **DDPM forward process**.
   - Train **DDPM & DDIM** on the **Sprites dataset**.
   - Compare **sampling speed** and **FID scores** for both models.
3. **Optimizing Sampling Speed**:

   - Implement **DDPM-ES** (Efficient Sampling).
   - Compare its effectiveness in reducing **sampling steps**.

---

### 🔥 **Score-Based Models**

Score-based models **estimate probability distributions** by learning **gradient fields** rather than explicit densities.

#### ✅ **Tasks:**

1. **Theoretical Analysis**:

   - Understand how **score functions** approximate distributions.
   - Explain why **Langevin dynamics** is needed for sampling.
2. **Implementing a Score-Based Model**:

   - Train a model to estimate **score functions** on **Mixture of Gaussians**.
   - Implement **Langevin dynamics** for generative sampling.
3. **Comparing Noise Schedules**:

   - Train models with **different noise levels**.
   - Analyze how noise affects **sampling accuracy**.

---

## ⚙️ Implementation Details

### **🔹 Dataset**

- The dataset used is **Sprites 16x16** (for diffusion models).
- For score-based models, a **Mixture of Gaussians** is used.
- **80/20 train-test split**.

### **🔹 Diffusion Model Architecture**

| **Component**       | **Details** |
| ------------------------- | ----------------- |
| **Base Model**      | UNet              |
| **Timesteps**       | 1000 (DDPM)       |
| **Noise Scheduler** | Linear            |
| **Training Loss**   | MSE               |

### **🔹 Training Parameters**

| Parameter     | Value  |
| ------------- | ------ |
| Learning Rate | 0.0002 |
| Batch Size    | 64     |
| Epochs        | 500    |

### **🔹 Score-Based Model Loss**

\[
L(\theta) = \frac{1}{2} \mathbb{E}_{p(x)} \left[ s_\theta(x)^2 \right] + \mathbb{E}_{p(x)} \left[ \nabla_x s_\theta(x) \right]
\]

---

## 📊 Mathematical Derivations

### **1️⃣ Diffusion Forward and Backward Processes**

- Show that **iterative noise addition** is unnecessary in DDPM.

### **2️⃣ Why is Langevin Dynamics Needed?**

- Score models require **iterative updates** for generating samples.

### **3️⃣ Computing FID Score**

- FID measures **feature space similarity** between real and generated samples:
  $$
  FID = ||\mu_r - \mu_g||^2 + Tr(\Sigma_r + \Sigma_g - 2(\Sigma_r \Sigma_g)^{1/2})
  $$

---

## 🚀 Training and Experimentation

1. **Train DDPM & DDIM** and compare **sample efficiency**.
2. **Train Score-Based Models** and evaluate **sampling quality**.
3. **Compute FID scores** to compare models.

---
