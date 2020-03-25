@inproceedings{nazeri2019edgeconnect,
  title={EdgeConnect: Generative Image Inpainting with Adversarial Edge Learning},
  author={Nazeri, Kamyar and Ng, Eric and Joseph, Tony and Qureshi, Faisal and Ebrahimi, Mehran},
  journal={arXiv preprint},
  year={2019},
}

# GNR-652-Project
Contains implementation of various papers that were read as part of the preparation for the problem statement, "Adversarial Impainting".

## Content
Consists of implementation of some GANs. Namely, [GAN] (https://arxiv.org/abs/1406.2661), [DCGAN] (https://arxiv.org/abs/1511.06434) and [WGAN] (https://arxiv.org/abs/1701.07875). The implementations are in their respective jupyter notebooks. The [GAN] (https://github.com/advaitkumar3107/GNR-652-Project/blob/master/GAN.ipynb) is trained on the MNIST dataset, whereas the [DCGAN] (https://github.com/advaitkumar3107/GNR-652-Project/blob/master/DCGAN.ipynb) and [WGAN] (https://github.com/advaitkumar3107/GNR-652-Project/blob/master/WGAN.ipynb) are trained on the [CelebA] (http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html) dataset. 

It also contains the implementation of the [EdgeConnect] (https://arxiv.org/abs/1901.00212) paper as discussed below:

### Edge-Connect
The code for [training] (https://github.com/advaitkumar3107/GNR-652-Project/blob/master/Edge_Connect_train.ipynb) as well as to perform [predictions] (https://github.com/advaitkumar3107/GNR-652-Project/blob/master/Edge_Connect_Predictions.ipynb) is attached above. I have used a few images from the [CelebA] (https://github.com/advaitkumar3107/GNR-652-Project/blob/master/celeba/img_align_celeba) dataset for training. The pre-trained [weights] (https://github.com/advaitkumar3107/GNR-652-Project/blob/master/weights) are also present(after training for about 350 epochs). Only regular masks were used as part of the training. The gram matrix computation function has been taken from the [official implementation] (https://github.com/knazeri/edge-connect). The hyperparameter values were also set according to the official implementation. I used a 80:20 split for the training:testing dataset size.

### Results
Since the epochs as well as the number of training images were less, the results are not as good as the official implementation. An example of a batch of predictions is as follows:
<p align='center'>  
  <img src='https://github.com/advaitkumar3107/GNR-652-Project/blob/master/edge_connect.png' width='870'/>
</p>
Above are the input images with masks. Masks are depicted in white. Below are the corresponding predictions made by our model.


