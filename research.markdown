---
layout: page
title: Research
permalink: /research/
math: true
---

### Machine-Learning Accelerated Calculations of Reduced Density Matrices

- **Principal Investigator (PI) Name:** Dr. [Jiabin Yu](https://www.phys.ufl.edu/wp/index.php/people/faculty/jiabin-yu/)
- **In Collaboration With:** Prof. Jiabin Yu (supervisor), [Lexu Zhao (Gavin)](https://sites.google.com/view/lexuzhao/about)
- **Institution and Department:** Department of Physics, College of Liberal Arts and Sciences, University of Florida
- **Timeline:** October 2024 - present
- **Research focus:** *n*-particle reduced density matrices (*n*-RDMs) play a central role in understanding correlated phases of matter, but their calculation is often computationally inefficient for strongly-correlated states at large system sizes. In this work, we use neural network (NN) architectures to accelerate and even predict *n*-RDMs for large systems. Our underlying intuition is that, for gapped states, *n*-RDMs are often smooth functions over the Brillouin zone (BZ) and therefore interpolable, allowing NNs trained on small-size to predict large-size ones. *(From the abstract of our [arXiv preprint](https://arxiv.org/abs/2511.07367))*.
- **Project responsibilities:** I am primarily responsible for the machine learning aspects of the project, including data preprocessing and postprocessing, as well as designing, implementing, and training neural networks, and fine-tuning their hyperparameters.
- **Sample Media:**  
![Figure showing percent reduction vs. L](/assets/images/hubbard_reduction_plot.png "NN for the Hubbard model")  
*Above:* Summary of results for the Hubbard model using a self-attention NN (*U = 1*) and SIRENs (*U = 1, 2, 3*) showing the percent reduction in the number of Hartree-Fock (HF) iterations as a function of the system size *L*. *See our [paper](https://arxiv.org/abs/2511.07367) for more!*
