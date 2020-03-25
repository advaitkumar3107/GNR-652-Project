# GNR-652-Project
Contains implementation of various papers that were read as part of the preparation for the problem statement, "Adversarial Impainting".

## Content
Consists of implementation of some GANs. Namely, [GAN] (https://arxiv.org/abs/1406.2661), [DCGAN] (https://arxiv.org/abs/1511.06434) and [WGAN] (https://arxiv.org/abs/1701.07875). The implementations are in their respective jupyter notebooks. The [GAN] (GAN.ipynb) is trained on the MNIST dataset, whereas the [DCGAN] (DCGAN.ipynb) and [WGAN] (WGAN.ipynb) are trained on the [CelebA] (http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html) dataset. 

It also contains the implementation of the [EdgeConnect] (https://arxiv.org/abs/1901.00212) paper as discussed below:

### Edge-Connect
The code for [training] (Edge_Connect_train.ipynb) as well as to perform [predictions] (Edge_Connect_Predictions.ipynb) is attached above. I have used a few images from the [CelebA] (celeba) dataset for training. The pre-trained [weights] (weights) are also present(after training for about 350 epochs). Only regular masks were used as part of the training.

### Results

