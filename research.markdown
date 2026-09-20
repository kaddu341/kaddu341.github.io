---
layout: page
title: Research
permalink: /research/
math: true
---

I work on machine learning for theoretical condensed-matter physics.

A full list of publications is available on [Google Scholar](https://scholar.google.com/citations?view_op=list_works&hl=en&user=Ryyb8UYAAAAJ) and in the [Curriculum Vitae](/resume/).

## Featured Project

### Reduced Density Matrices Through Machine Learning

- **Principal Investigator (PI) Name:** Prof. [Jiabin Yu](https://www.phys.ufl.edu/wp/index.php/people/faculty/jiabin-yu/)
- **In Collaboration With:** Prof. Jiabin Yu (supervisor), [Lexu Zhao (Gavin)](https://sites.google.com/view/lexuzhao/about)
- **Institution and Department:** Department of Physics, College of Liberal Arts and Sciences, University of Florida
- **Timeline:** October 2024 - present
- **Research focus:** *n*-particle reduced density matrices (*n*-RDMs) play a central role in understanding correlated phases of matter, but their calculation is often computationally inefficient for strongly-correlated states at large system sizes. In this work, we use neural network (NN) architectures to accelerate and even predict *n*-RDMs for large systems. Our underlying intuition is that, for gapped states, *n*-RDMs are often smooth functions over the Brillouin zone (BZ) and are therefore interpolable, allowing NNs trained on small-size systems to predict large-size ones. We devise two architectures: a self-attention NN that maps random RDMs to physical ones, and a Sinusoidal Representation Network (SIREN) that maps momentum-space coordinates directly to RDM values. Trained on small meshes, these networks provide high-quality initial guesses for Hartree-Fock (HF) at much larger system sizes, reducing the required number of iterations by up to 92% compared to random initializations. *See our [arXiv preprint](https://arxiv.org/abs/2511.07367) for the full results.*
- **Project responsibilities:** Primarily responsible for the machine learning aspects of the project, including data preprocessing and postprocessing, as well as designing, implementing, and training neural networks, and fine-tuning their hyperparameters.
- **Follow-up work:** Also contributed to a study led by [Justin Hart](https://justin.hart.science/), extending the method to fractional Chern insulators. It introduces representability-aware networks, which either interpolate 2-RDMs onto larger momentum meshes or are optimized directly as a variational ansatz by energy minimization ([arXiv:2605.20326](https://arxiv.org/abs/2605.20326)).
- **Sample Media:**  
![Figure showing percent reduction vs. L](/assets/images/hubbard_reduction_plot.png "NN for the Hubbard model")  
*Above:* Summary of results for the Hubbard model using a self-attention NN (*U = 1*) and SIRENs (*U = 1, 2, 3*) showing the percent reduction in the number of Hartree-Fock (HF) iterations as a function of the system size *L*. *See our [paper](https://arxiv.org/abs/2511.07367) for more!*
