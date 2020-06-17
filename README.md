# gan-experiments
This repository is populated with my experiments using different gan architectures and training techniques.
My motivation to make this is to provide myself and others a useful reference with simple to read code, training logic, expected loss curves, all in tensorflow 2. 

# WGAN-GP
Wasserstien GAN with gradient penalty. WGANS were first introduced in [Wasserstein GAN](https://arxiv.org/pdf/1701.07875.pdf). Unlike the vanilla GAN architecture, a critic which scores the realness (or fakeness) of a generation replaces the discriminator. The basis of the training logic is first training the critic to convergence, then training the generator to learn from it. This is analogous to a teacher-student relationship. In order to achieve this the critic is trained multiple times per every generator train step. There is also a requirement for the critic to model a 1-Lipschitz continuous function. This was first done by clipping the weights of the critic but later this was imporved in the WGAN-GP architecture introduced in [Improved Training of Wasserstein GANs](https://arxiv.org/pdf/1704.00028.pdf).

# DRAGAN
DRAGANs introduced in [On Convergence and Stability of GANs](https://arxiv.org/pdf/1705.07215.pdf) modifies the gradient penalty of WGAN-GPs slightly by only providing a penalty along the real data manifold, instead of the manifold obtained by interpolating real and generated data. This was proven to stabalize training even more and converge quicker.
