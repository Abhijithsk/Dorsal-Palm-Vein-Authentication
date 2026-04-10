# CNN-Based Dorsal Hand Vein Authentication Using Triplet Loss Metric Learning

[![Published](https://img.shields.io/badge/Published-IJARCCE%20March%202026-blue)](https://doi.org/10.17148/IJARCCE.2026.15372)
[![Impact Factor](https://img.shields.io/badge/Impact%20Factor-8.471-brightgreen)](https://ijarcce.com)
[![DOI](https://img.shields.io/badge/DOI-10.17148%2FIJARCCE.2026.15372-orange)](https://doi.org/10.17148/IJARCCE.2026.15372)
[![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)](https://pytorch.org)

> Published research — undergraduate project, College of Engineering Kottarakkara, Kerala, India.

---

## Publication details

| Field | Details |
|-------|---------|
| Journal | IJARCCE — International Journal of Advanced Research in Computer and Communication Engineering |
| Volume | 15, Issue 3 |
| Month | March 2026 |
| DOI | [10.17148/IJARCCE.2026.15372](https://doi.org/10.17148/IJARCCE.2026.15372) |
| ISSN (Online) | 2278-1021 |
| ISSN (Print) | 2319-5940 |
| Impact Factor | 8.471 |
| Indexing | Google Scholar, Crossref, Mendeley |
| Standard | Meets UGC Parameters |

---

## Abstract

This paper presents a biometric authentication system based on **dorsal hand vein patterns** — the network of veins visible on the back of the hand. Unlike fingerprints or face recognition, vein patterns are internal and extremely difficult to spoof.

We use a **Convolutional Neural Network (CNN)** as the feature extractor combined with **Triplet Loss Metric Learning** to train the system. Instead of classifying fixed identities, triplet loss trains the network to produce embeddings where:
- Samples from the **same person** are pulled **closer together** in embedding space
- Samples from **different people** are pushed **further apart**

This metric learning approach makes the system naturally extensible to new users without retraining the full model.

---

## How it works

```
Input: Dorsal hand vein image (NIR camera)
         │
         ▼
    Preprocessing
    (CLAHE enhancement, normalization, resizing)
         │
         ▼
    CNN Feature Extractor
    (Convolutional layers → pooling → dense)
         │
         ▼
    128-dim Embedding Vector
         │
         ▼
    Triplet Loss Training
    (Anchor · Positive · Negative triplets)
         │
         ▼
    Embedding Space
    Same person → close vectors
    Different person → distant vectors
         │
         ▼
    Authentication Decision
    (Euclidean distance threshold)
```

---

## Key concepts

### Triplet loss

The model is trained on triplets: **(Anchor, Positive, Negative)**

- **Anchor** — a reference vein image of person A
- **Positive** — another image of person A (same identity)
- **Negative** — an image of person B (different identity)

The loss function minimizes the distance between Anchor and Positive while maximizing the distance between Anchor and Negative:

```
L = max(d(A, P) - d(A, N) + margin, 0)
```

This forces the CNN to learn meaningful, identity-discriminative features rather than just memorizing training classes.

### Why dorsal hand veins?

- Internal biometric — cannot be lifted like fingerprints
- Stable throughout adult life
- Works with near-infrared (NIR) imaging
- Non-contact and hygienic

---

## Authors

- **Abhijith S Kurup** — [GitHub](https://github.com/Abhijithsk) · [LinkedIn](https://www.linkedin.com/in/abhijith-s-kurup-992b9b24a)
- J Adithye
- Abhimanyu R
- Adithiya S
- Girija V R

Department of Computer Science, College of Engineering Kottarakkara, Kerala, India
APJ Abdul Kalam Technological University

---

## Citation

```bibtex
@article{kurup2026vein,
  title     = {CNN-Based Dorsal Hand Vein Authentication Using Triplet Loss Metric Learning},
  author    = {Kurup, Abhijith S and Adithye, J and R, Abhimanyu and S, Adithiya and V R, Girija},
  journal   = {IJARCCE},
  volume    = {15},
  number    = {3},
  year      = {2026},
  doi       = {10.17148/IJARCCE.2026.15372},
  issn      = {2278-1021}
}
```

---

## Related

- [Facio Music](https://github.com/Abhijithsk/Faciomusic) — Facial emotion recognition music player
- [AI Art Generator](https://github.com/Abhijithsk/AI-ART-GENERATOR) — Generative AI image synthesis
