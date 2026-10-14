<div align="center">

# Mathematics for AI / ML / LLM

### The Complete Math Foundation You Need to Master AI

[![GitHub stars](https://img.shields.io/github/stars/GizzZmo/math-for-llms?style=for-the-badge&logo=github&color=yellow)](https://github.com/GizzZmo/math-for-llms/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/GizzZmo/math-for-llms?style=for-the-badge&logo=github&color=blue)](https://github.com/GizzZmo/math-for-llms/network/members)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)
[![Notebooks](https://img.shields.io/badge/Jupyter_Notebooks-229-orange?style=for-the-badge&logo=jupyter)](.)
[![Chapters](https://img.shields.io/badge/Chapters-25-brightgreen?style=for-the-badge&logo=bookstack)](.)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=for-the-badge)](CONTRIBUTING.md)

**A structured, open-source curriculum covering 25 domains of mathematics essential for AI, Machine Learning, and Large Language Models — from foundational concepts to cutting-edge research.**

[Get Started](#-quick-start) · [Roadmap](#-learning-roadmap) · [Chapters](#-chapters) · [Resources](#-resources) · [Contributing](#-contributing)

---

<br>

<img src="https://img.shields.io/badge/115-Interactive_Theory_Notebooks-blue?style=flat-square&logo=jupyter" alt="Theory notebooks" />
<img src="https://img.shields.io/badge/114-Exercise_Notebooks-green?style=flat-square&logo=jupyter" alt="Exercise notebooks" />
<img src="https://img.shields.io/badge/115-Detailed_Notes-red?style=flat-square&logo=markdown" alt="Notes files" />

</div>

<br>

## Why This Repo?

Most AI/ML learners hit the **math wall** — papers full of symbols that feel alien, optimization steps that seem like magic, and model architectures that assume deep mathematical fluency.

This repository bridges that gap with a **learn-by-doing** approach:

- **Structured path** from high school math to research-level topics
- **Notes → Theory → Exercises** flow for every topic
- **Interactive Jupyter notebooks** with visualizations, not just formulas
- **Real ML connections** — every concept links to practical AI applications
- **Self-contained** — no prerequisites beyond basic algebra

> _"The math you need depends on what you're building — this repo helps you find exactly that."_

---

## Financial & Causal Applications Highlight

Graph Neural Networks (Chapter 11) combined with Causal Inference (Chapter 22) enable modeling of **default contagion** and **heterogeneous treatment effects** in financial networks:

- Firm/counterparty nodes + payment/supply-chain edges → GATv2 embeddings that capture k-hop spillover risk.
- Graph embeddings as covariates inside Double/Debiased Machine Learning for policy evaluation (liquidity support, credit-line adjustments).
- Attention and GraphSHAP explanations for regulatory compliance (EU AI Act, GDPR Art. 22).

See [11-Graph-Theory/05-Graph-Neural-Networks](11-Graph-Theory/05-Graph-Neural-Networks/notes.md#126-financial-networks-credit-risk-and-default-contagion) and the cross-reference in Chapter 22.

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/GizzZmo/math-for-llms.git
cd math-for-llms

# Set up the environment
python3 -m venv .venv
source .venv/bin/activate   # Windows: .venv\\Scripts\\Activate.ps1

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter lab
```

Each topic follows a **3-step learning flow**:

```
📖 notes.md          → Read the concepts and intuition
🔬 theory.ipynb      → Explore interactive demonstrations
✏️ exercises.ipynb   → Test your understanding
```

---

## 🗺️ Learning Roadmap

The curriculum covers **25 domains** organized in **8 phases**. Each phase builds on the previous one. Topics marked with ★ are critical for ML/AI.

```
  START HERE
      │
      ▼
 ┌─────────┐     ┌──────────────┐     ┌──────────┐     ┌──────────────┐
 │ Phase 1  │ ──▶ │   Phase 2   │ ──▶ │ Phase 3  │ ──▶ │   Phase 4    │
 │ Core     │     │ Probability │     │ Learning │     │ Deeper       │
 │ Math     │     │ & Stats     │     │ Engines  │     │ Theory       │
 └─────────┘     └─────────────┘     └──────────┘     └──────────────┘
                                                              │
      ┌───────────────────────────────────────────────────────────────┘
      ▼
 ┌──────────┐     ┌──────────┐     ┌──────────────┐     ┌──────────────┐
 │ Phase 5  │ ──▶ │ Phase 6  │ ──▶ │   Phase 7    │ ──▶ │   Phase 8    │
 │ ML Math  │     │ LLM Math │     │ Production   │     │ Research     │
 │          │     │          │     │ & Safety     │     │ Frontiers    │
 └──────────┘     └──────────┘     └──────────────┘     └──────────────┘
```

---

### Phase 1 — Core Math Foundations `Ch. 01 → 02 → 04 → 05`

> The mathematical language everything else is built on.

```
① MATHEMATICAL FOUNDATIONS (Ch.01)
├── Number Systems (ℕ ℤ ℚ ℝ ℂ)
├── Sets & Logic
├── Functions & Mappings
├── Σ Summation & Product Notation
├── Einstein Summation & Index Notation
└── Proof Techniques (induction, contradiction, direct)
        │
        ├──────────────────────────────────────────────────┐
        ▼                                          ▼
② LINEAR ALGEBRA (Ch.02 + Ch.03)            ③ CALCULUS (Ch.04 + Ch.05)
├── Vectors & Spaces                        ├── Limits & Continuity
├── Matrix Operations                       ├── Derivatives & Differentiation
├── Systems of Equations                    ├── Integration & Series
├── Determinants & Rank                     ├── Partial Derivatives & Gradients
├── Eigenvalues & Eigenvectors ★            ├── Jacobians & Hessians ★
├── SVD ★                                   ├── Chain Rule → Backpropagation ★
├── PCA                                     ├── Optimality Conditions
├── Orthogonality & Norms                   └── Automatic Differentiation ★
├── Positive Definite Matrices
└── Matrix Decompositions (LU/QR/Cholesky)
```

---

### Phase 2 — Probabilistic Thinking `Ch. 06 → 07`

> How to reason about uncertainty — the foundation of all ML inference.

```
④ PROBABILITY & STATISTICS (Ch.06 + Ch.07)
├── Random Variables & Distributions
├── Joint Distributions
├── Expectation & Moments
├── Concentration Inequalities
├── Stochastic Processes
├── Markov Chains ★
├── Descriptive Statistics
├── Estimation Theory & MLE
├── Bayesian Inference ★
├── Hypothesis Testing
├── Time Series
└── Regression Analysis
```

---

### Phase 3 — Making Models Learn `Ch. 08 → 09`

> The algorithms that train every model and the theory behind loss functions.

```
⑤ OPTIMIZATION (Ch.08)                     ⑥ INFORMATION THEORY (Ch.09)
├── Convex Optimization ★                  ├── Entropy (Shannon) ★
├── Gradient Descent (SGD/Mini-batch) ★    ├── KL Divergence ★
├── Second-Order Methods (Newton/BFGS)     ├── Mutual Information ★
├── Constrained Optimization (KKT)         ├── Cross-Entropy ★
├── Stochastic Optimization ★              └── Fisher Information
├── Optimization Landscape
├── Adaptive LR (Adam / RMSProp) ★
├── Regularization (L1/L2/Dropout)
├── Hyperparameter Optimization
└── Learning Rate Schedules
```

---

### Phase 4 — Deeper Theory `Ch. 03 → 10 → 11 → 12`

> Specialized math that powers specific ML architectures.

```
⑦ NUMERICAL METHODS (Ch.10)                ⑧ GRAPH THEORY (Ch.11)
├── Floating-Point Arithmetic              ├── Graph Basics & Representations
├── Numerical Linear Algebra               ├── Graph Algorithms
├── Numerical Optimization                 ├── Spectral Graph Theory ★
├── Interpolation & Approximation          ├── Graph Neural Networks ★
└── Numerical Integration                  └── Random Graphs

⑨ FUNCTIONAL ANALYSIS (Ch.12)
├── Normed Spaces
├── Hilbert Spaces ★
└── Kernel Methods (SVM / GP) ★
```

---

### Phase 5 — ML Math in Practice `Ch. 13 → 14`

> The math that directly appears inside ML models.

```
                        ╔══════════════════╗
                        ║  ML-SPECIFIC MATH  ║
                        ╚══════════════════╝
                                 │
          ┌─────────────────────┬───────────────────────┐
          ▼                      ▼                      ▼
⑩ ML MATH CORE (Ch.13)   ⑪ DEEP LEARNING (Ch.14)   ⑫ RL (Ch.14)
├── Loss Functions ★      ├── Neural Net Math ★      ├── MDP (State/Action)
├── Activation Fns ★      ├── CNN & Convolution ★    ├── Bellman Equations ★
├── Normalization ★       ├── RNN & LSTM Math ★      ├── Policy Gradient ★
└── Sampling Methods      ├── Transformer ★          ├── Value Functions ★
                          ├── Generative (VAE/GAN)   └── Actor-Critic
                          └── Probabilistic Models
```

---

### Phase 6 — LLM Math `Ch. 15 → 16`

> Everything that makes Large Language Models work under the hood.

```
                         ╔════════════════╗
                         ║  MATH FOR LLMs   ║
                         ╚════════════════╝
                                  │
       ┌─────────────────────────┬──────────────────────────┐
       ▼                          ▼                          ▼
⑬ ATTENTION & ARCH         ⑭ TRAINING AT SCALE       ⑮ DATA PIPELINE
   (Ch.15)                    (Ch.15)                    (Ch.16)
├── Tokenization            ├── Scaling Laws ★         ├── Data Format Standards
├── Embedding Space         ├── Training at Scale      ├── JSONL Generation
├── Attention Mech ★        ├── Efficient Attention    ├── Quality Checks
├── Positional Enc ★        ├── MoE & Routing          ├── Dataset Assembly
└── LM Probability ★       ├── Quantization           ├── Contamination & Dedup
                            ├── Distillation           ├── Documentation
                            └── RAG & Retrieval        └── Data Mixture Optimization
```

---

### Phase 7 — Production & Safety `Ch. 17 → 18 → 19`

> Ship models responsibly — evaluate, align, and monitor.

```
⑯ EVALUATION (Ch.17)           ⑰ ALIGNMENT & SAFETY (Ch.18)     ⑱ PRODUCTION (Ch.19)
├── Capability Benchmarks      ├── SFT Math ★                    ├── Data Versioning & Lineage
├── Calibration & Uncertainty  ├── RLHF Math ★                   ├── Experiment Tracking
├── Robustness &               ├── DPO / Preference Opt ★        ├── Feature Stores &
│   Distribution Shift         ├── Policy & Guardrails           │   Data Contracts
├── Error Analysis &           └── Human-in-the-Loop             ├── Model Serving &
│   Ablations                      & Monitoring                  │   Inference Optimization
└── A/B Testing &                                                ├── Monitoring, Drift
    Experimentation                                              │   & Retraining
                                                                 └── LLM Observability
                                                                     & Guardrails
```

---

### Phase 8 — Research Frontiers `Ch. 20 → 21 → 22 → 23 → 24 → 25`

> Advanced theory for research-level understanding.

```
⑲ FOURIER & SIGNALS (Ch.20)    ⑳ STATISTICAL LEARNING (Ch.21)   ⑴ CAUSAL INFERENCE (Ch.22)
├── Fourier Series              ├── PAC Learning                  ├── Structural Causal Models
├── Fourier Transform           ├── VC Dimension                  ├── Do-Calculus
├── DFT & FFT                  ├── Bias-Variance Tradeoff        ├── Counterfactuals
├── Convolution Theorem         ├── Generalization Bounds         └── Causal Discovery
└── Wavelets                    └── Rademacher Complexity

⑵ GAME THEORY (Ch.23)          ⑶ MEASURE THEORY (Ch.24)         ⑷ DIFF. GEOMETRY (Ch.25)
├── Nash Equilibria             ├── Sigma-Algebras                ├── Manifolds
├── Minimax Theorem             ├── Lebesgue Integration          ├── Riemannian Geometry
├── Multi-Agent Systems         ├── Probability Measure Spaces    ├── Geodesics
└── Adversarial Game Theory     └── Radon-Nikodym Theorem         └── Optimization on Manifolds
```

```
╔════════════════════════════════════════════════════════════════╗
║                                                               ║
║        ★  YOU ARE NOW A MATH-FOR-AI WIZARD  ★                 ║
║                                                               ║
║        ★ = Critical for ML/AI — prioritize these topics       ║
║                                                               ║
╚════════════════════════════════════════════════════════════════╝
```

### Quick Reference — Learning Order

| Phase                                | Chapters                    | Focus                                                       |
| :----------------------------------- | :-------------------------- | :---------------------------------------------------------- |
| **Phase 1** — Core Foundations       | 01 → 02 → 04 → 05           | Numbers, vectors, matrices, derivatives, gradients          |
| **Phase 2** — Probabilistic Thinking | 06 → 07                     | Random variables, distributions, estimation, inference      |
| **Phase 3** — Making Models Learn    | 08 → 09                     | Optimization algorithms, information-theoretic losses       |
| **Phase 4** — Deeper Theory          | 03 → 10 → 11 → 12           | Advanced linear algebra, numerical methods, graphs, kernels |
| **Phase 5** — ML Math in Practice    | 13 → 14                     | Loss functions, activations, architecture-specific math     |
| **Phase 6** — LLM Math               | 15 → 16                     | Attention, embeddings, scaling laws, training pipelines     |
| **Phase 7** — Production & Safety    | 17 → 18 → 19                | Evaluation, alignment (RLHF/DPO), MLOps                     |
| **Phase 8** — Research Frontiers     | 20 → 21 → 22 → 23 → 24 → 25 | Fourier analysis, learning theory, causality, geometry      |

---

## 📚 Chapters

### Core Mathematics

<details>
<summary><b>01 · Mathematical Foundations</b> — Number systems, sets, logic, proofs</summary>
<br>

| Topic                        | Description                                                       |
| :--------------------------- | :---------------------------------------------------------------- |
| Number Systems               | Natural, integer, rational, real, and complex numbers (N Z Q R C) |
| Sets & Logic                 | Set operations, propositional logic, quantifiers                  |
| Functions & Mappings         | Domain, range, injectivity, surjectivity, composition             |
| Summation & Product Notation | Sigma/Pi notation, index manipulation                             |
| Einstein Summation           | Index notation used in tensor operations                          |
| Proof Techniques             | Induction, contradiction, direct proof, contrapositive            |

</details>

<details>
<summary><b>02 · Linear Algebra Basics</b> — Vectors, matrices, systems of equations</summary>
<br>

| Topic                     | ML Connection                            |
| :------------------------ | :--------------------------------------- |
| Vectors & Spaces          | Feature representations, embeddings      |
| Matrix Operations         | Forward propagation, transformations     |
| Systems of Equations      | Linear regression (normal equations)     |
| Determinants              | Change of variables in normalizing flows |
| Matrix Rank               | Model capacity, low-rank approximations  |
| Vector Spaces & Subspaces | Dimensionality, feature spaces           |

</details>

<details>
<summary><b>03 · Advanced Linear Algebra</b> — Eigen decomposition, SVD, PCA</summary>
<br>

| Topic                          | ML Connection                                 |
| :----------------------------- | :-------------------------------------------- |
| Eigenvalues & Eigenvectors     | PCA, spectral clustering, stability analysis  |
| Singular Value Decomposition   | Recommender systems, dimensionality reduction |
| Principal Component Analysis   | Feature extraction, data compression          |
| Linear Transformations         | Neural network layers as transforms           |
| Orthogonality & Orthonormality | Gram-Schmidt, decorrelated features           |
| Matrix Norms                   | Regularization, operator bounds               |
| Positive Definite Matrices     | Covariance matrices, kernel validity          |
| Matrix Decompositions          | LU, QR, Cholesky — efficient solvers          |

</details>

<details>
<summary><b>04 · Calculus Fundamentals</b> — Limits, derivatives, integrals, series</summary>
<br>

| Topic                         | ML Connection                                  |
| :---------------------------- | :--------------------------------------------- |
| Limits & Continuity           | Convergence guarantees, activation smoothness  |
| Derivatives & Differentiation | Gradient computation for all parameters        |
| Integration                   | Probability densities, normalization constants |
| Series & Sequences            | Taylor approximations, convergence analysis    |

</details>

<details>
<summary><b>05 · Multivariate Calculus</b> — Gradients, Jacobians, back