# GNR-652-Project
Contains implementation of various papers that were read as part of the preparation for the problem statement, "Adversarial Impainting".

## Content
Consists of implementation of some GANs. Namely, [GAN](https://arxiv.org/abs/1406.2661), [DCGAN](https://arxiv.org/abs/1511.06434) and [WGAN](https://arxiv.org/abs/1701.07875). The implementations are in their respective jupyter notebooks. The [GAN](https://github.com/advaitkumar3107/GNR-652-Project/blob/master/GAN.ipynb) is trained on the MNIST dataset, whereas the [DCGAN](https://github.com/advaitkumar3107/GNR-652-Project/blob/master/DCGAN.ipynb) and [WGAN](https://github.com/advaitkumar3107/GNR-652-Project/blob/master/WGAN.ipynb) are trained on the [CelebA](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html) dataset. 

It also contains the implementation of the [EdgeConnect](https://arxiv.org/abs/1901.00212) paper as discussed below:

### Edge-Connect
The code for [training](https://github.com/advaitkumar3107/GNR-652-Project/blob/master/Edge_Connect_train.ipynb) as well as to perform [predictions](https://github.com/advaitkumar3107/GNR-652-Project/blob/master/Edge_Connect_Predictions.ipynb) is attached above. I have used a few images from the [CelebA](https://github.com/advaitkumar3107/GNR-652-Project/blob/master/celeba/img_align_celeba) dataset for training. The pre-trained [weights](https://github.com/advaitkumar3107/GNR-652-Project/blob/master/weights) are also present(after training for about 350 epochs). Only regular masks were used as part of the training. The gram matrix computation function has been taken from the [official implementation](https://github.com/knazeri/edge-connect). The hyperparameter values were also set according to the official implementation. I used a 80:20 split for the training:testing dataset size.

### Model Architecture
<p align='center'>  
  <img src='https://github.com/advaitkumar3107/GNR-652-Project/blob/master/Model_Architecture.png' width='870'/>
</p>
Above shown is the architecture as well as the working of the model in brief. The model consists of two GANs. The concatenation of the mask, grayscale image(with mask applied) and edge map(with mask applied) is fed into the first GAN, which outputs the completed edge map(which fills in the missing edge in the mask region). This is then concatenated with the original colour image(with mask) and fed into the second GAN which fills in the colour of the image and gives us the completed image.

### Results
Since the epochs as well as the number of training images were less, the results are not as good as the official implementation. An example of a batch of predictions is as follows:
<p align='center'>  
  <img src='https://github.com/advaitkumar3107/GNR-652-Project/blob/master/edge_connect.png' width='870'/>
</p>
Above are the input images with regular masks. Masks are depicted in white. 

Next we trained the model on irregular masks(salt and pepper noise) as well. We trained it for 10 epochs on this noise ranging from 10% of the input masked to 60% of it masked(with increments of 10%). Below are the results while testing

#### AT 10%
<p align='center'>  
  <img src='https://github.com/advaitkumar3107/GNR-652-Project/blob/master/results/10%.png' width='870'/>
</p>
#### AT 20%
<p align='center'>  
  <img src='https://github.com/advaitkumar3107/GNR-652-Project/blob/master/results/20%.png' width='870'/>
</p>
#### AT 30%
<p align='center'>  
  <img src='https://github.com/advaitkumar3107/GNR-652-Project/blob/master/results/30%.png' width='870'/>
</p>
#### AT 40%
<p align='center'>  
  <img src='https://github.com/advaitkumar3107/GNR-652-Project/blob/master/results/40%.png' width='870'/>
</p>
#### AT 50%
<p align='center'>  
  <img src='https://github.com/advaitkumar3107/GNR-652-Project/blob/master/results/50%.png' width='870'/>
</p>
#### AT 60%
<p align='center'>  
  <img src='https://github.com/advaitkumar3107/GNR-652-Project/blob/master/results/60%.png' width='870'/>
</p>
#### AT 70%
<p align='center'>  
  <img src='https://github.com/advaitkumar3107/GNR-652-Project/blob/master/results/70%.png' width='870'/>
</p>
#### AT 80%
<p align='center'>  
  <img src='https://github.com/advaitkumar3107/GNR-652-Project/blob/master/results/80%.png' width='870'/>
</p>
#### AT 90%
<p align='center'>  
  <img src='https://github.com/advaitkumar3107/GNR-652-Project/blob/master/results/90%.png' width='870'/>
</p>
As we can see, the de-noising gets better as the percent of pixels masked increases, with the best results at around 50% of the input masked. The accuracy again decreases as the amount of pixels masked increases.
