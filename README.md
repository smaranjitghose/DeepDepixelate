# DeepDepixelate 🕵️‍♀️
We’ve all seen that moment in a crime thriller where the hero asks the tech guy to zoom and enhance an image, number plates become readable, pixelated faces become clear and whatever evidence needed to solve the case is found.
And, we’ve all scoffed, laughed and muttered something under our breath about how lost information can’t be restored.
Not any more. Well, sort of. It turns out the information is only partly lost. In a similar way that as humans we might infer the detail of a blurry image based on what we know about the world, now we can successfully apply the same logic to images to recover ‘photorealistic’ details lost to resolution effects.
This is the essence of Super Resolution, unlocking information on the sub pixel scale through a complicated understanding of the translation of low to high resolution images.

# Background:

To achieve this we implement [Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network](https://arxiv.org/abs/1609.04802)

Generative adversarial networks (GANs) provide a powerful framework for generating plausible-looking natural images with high perceptual quality. The GAN procedure encourages the reconstructions to move towards regions of the search space with high probability of containing photo-realistic images and thus closer to the natural image manifold.

SRGAN is a GAN based network, where the generator (G) learns to generates SR images from LR images as close as possible to HR. The discriminator (D) learns to distinguish generated SR images from real images. The G takes advantage of ResNet and sub-pixel convolution for upsampling. It also combines perceptual loss with generative or adversarial loss for the computation of its loss.
#### Architecture:
It mostly composes of convolution layers, batch normalization and parameterized ReLU (PRelU). The generator also implements skip connections similar to ResNet. The convolution layer with “k3n64s1” stands for 3x3 kernel filters outputting 64 channels with stride 1.
![SRGAN Architecture](https://github.com/smaranjitghose/DeepDepixelate/blob/master/assets/srgan_architecture.png)
#### Loss Function
The loss function for the generator composes of the content loss (reconstruction loss) and the adversarial loss.
![SRGAN Perceptual Loss Function](https://github.com/smaranjitghose/DeepDepixelate/blob/master/assets/srgan_perceptual_loss.png)

# Usage:🐱‍💻
- Download the [Celeba Dataset](https://www.dropbox.com/sh/8oqt9vytwxb3s4r/AADIKlz8PR9zr6Y20qbkunrba/Img/img_align_celeba.zip?dl=0)
(if not available there see if options are listed at http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html)
- Clone this repo
- Open the Terminal and then ```cd DeepDepixelate```
- Now Run the script as ```python pysrgan.py```



