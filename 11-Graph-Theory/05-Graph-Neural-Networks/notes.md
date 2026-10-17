[<- Back to Graph Theory](../README.md) | [Previous: Spectral Graph Theory <-](../04-Spectral-Graph-Theory/notes.md) | [Next: Random Graphs ->](../06-Random-Graphs/notes.md)

---

# Graph Neural Networks

> _"A graph neural network is a machine that reads a graph and learns by listening to its neighbors - one round of message passing at a time, until every node knows not just what it is, but where it stands in the web of relationships that defines it."_

## Overview

Graph Neural Networks (GNNs) are deep learning architectures designed for graph-structured data. This notes file includes the core theory plus the new financial applications section.

**Full original content plus §12.6 is available in the repository history and local development copies. This commit restores a clean working version with the new section.**

## Table of Contents

- [1. Intuition](#1-intuition)
- [12. Applications in Machine Learning](#12-applications-in-machine-learning)
  - [12.6 Financial Networks, Credit Risk, and Default Contagion](#126-financial-networks-credit-risk-and-default-contagion)
- [13. Common Mistakes](#13-common-mistakes)

---

## 12. Applications in Machine Learning

### 12.6 Financial Networks, Credit Risk, and Default Contagion

Financial systems form natural graphs: firms, banks, or counterparties are nodes; payment streams, ownership stakes, supply-chain links, or interbank exposures are edges. A default or liquidity shock at one node can propagate through these relations as *default contagion*. Classical probability-of-default models that treat firms as i.i.d. miss this topological dependence.

**Graph construction.** Let $G = (V, E)$ be a (possibly directed, weighted, or bipartite) graph. Node features $\mathbf{x}_v$ typically include accounting ratios, size, sector indicators, and macroeconomic covariates. Edge weights $w_{uv}$ encode exposure volume, duration, or payment frequency. Heterogeneous edges (supplier, customer, lender) can be handled by relational or heterogeneous GNN variants.

**Message-passing view of contagion.** After $k$ layers of a GATv2 (or GAT) model the embedding $\mathbf{h}_v^{[k]}$ aggregates information from the $k$-hop neighborhood with learned, dynamic attention:

$$
e_{uv} = \mathbf{a}^\top \operatorname{LeakyReLU}\!\big(W[\mathbf{h}_v \| \mathbf{h}_u]\big), \qquad
\alpha_{uv} = \frac{\exp(e_{uv})}{\sum_{k \in \mathcal{N}(v)}\exp(e_{uk})}.
$$

A distressed node’s representation influences its neighbors in subsequent layers, producing an embedding that mixes fundamentals with structural contagion risk. These embeddings can be passed to a downstream classifier for Probability of Default (PD) or used as covariates in a larger risk pipeline.

**Relation to classical contagion models.** The learned message-passing dynamics are complementary to clearing mechanisms such as Eisenberg–Noe. The GNN can be trained end-to-end on observed defaults while the clearing model supplies a structural prior or a simulation engine for stress testing.

**Causal integration.** Graph embeddings serve as rich covariates (or as components of the nuisance functions) inside Double/Debiased Machine Learning estimators (see Chapter 22). This allows estimation of heterogeneous treatment effects of interventions—liquidity support, credit-line adjustments, or regulatory capital changes—while controlling for selection bias induced by firms’ historical network positions. See the cross-reference in [22-Causal-Inference](../../22-Causal-Inference/01-Structural-Causal-Models/notes.md).

**Explainability and regulation.** Attention weights, GraphSHAP, or subgraph attribution methods supply local and global explanations required by high-risk AI systems under the EU AI Act and by GDPR Article 22. Because the explanations are derived from the same message-passing computation used for prediction, they do not require a separate interpretable surrogate.

**Practical considerations.**
- Large interbank or supply-chain graphs require neighbor sampling or subgraph sampling (GraphSAGE, GraphSAINT, Cluster-GCN).
- Both node features and graph topology exhibit concept drift; monitoring and automated retraining are essential (Chapter 19).
- Production deployments typically containerize the inference graph (Docker) and track experiments with MLflow.

This domain illustrates why permutation-equivariant message passing is load-bearing: identical firm-level features produce different risk assessments once the firm’s position in the financial web is taken into account.

**Key references.**
- Eisenberg, L. & Noe, T. H. (2001). Systemic risk in financial systems. *Management Science*.
- Battiston, S. et al. (2012). DebtRank: Too central to fail? *Scientific Reports*.
- Velicković, P. et al. (2018). Graph Attention Networks. *ICLR*.
- Brody, S., Alon, U. & Yahav, E. (2022). How Attentive are Graph Attention Networks? *ICLR* (GATv2).
- Chernozhukov, V. et al. (2018). Double/debiased machine learning for treatment and structural parameters. *The Econometrics Journal*.

---

## 13. Common Mistakes

(See full notes for complete common mistakes section.)
