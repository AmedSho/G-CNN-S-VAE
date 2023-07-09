# Learning Rotation-Agnostic Representations via Group Equivariant VAES

An emerging field in representation learning involves the study of group-equivariant neural networks, that leverage concepts from group representation theory to design neural architectures that can exploit discrete and continuous symmetries to produce more general representations. Following this direction, in this work we demonstrate how an image embedding agnostic to rotations can be naturally obtained by training a variational autoencoder ($\mathcal{S}$-VAE) equipped with a Group equivariant Convolutional Neural Network (G-CNN) encoder.

![](https://github.com/AmedSho/G-CNN-S-VAE/blob/main/S-VAE.png)

In the repository there is a folder with the project and the entire code we used for the project, which can be also easly found here: https://www.kaggle.com/code/amedsho/s-gcnn-vae

VAE results over randomly rotated inputs:
![](https://github.com/AmedSho/G-CNN-S-VAE/blob/main/Project/VAE_results.png)

# Are 6s just rotated 9s?

In our work we compared $\mathcal{S}$-GVAE with a standard $\mathcal{S}$-VAE of the same size (∼ 800k params), both trained on non-rotated MNIST. We used a pre-trained ResNet50 (∼ 23.5M params) to classify the generated outputs from the two models (just 6s and 9s).
Below the results:

| input  | $\mathcal{S}$-GVAE |  $\mathcal{S}$-VAE |
| ------------- | ------------- | ------------- |
| Rotated 6 digits  | 95%  | 24% |
| Rotated 9 digits | 66%  | 28% |

![](https://github.com/AmedSho/G-CNN-S-VAE/blob/main/Project/comparison_6_9.png)

The strong performance in discriminating between 6s and 9s suggests that the rotational orientation of these digits does not play a significant role in recognition. As such, it is unlikely that 6s are simply rotated 9s. However, the differential performance between these digits may be attributed to variations in handwriting style. While the 6-digit maintains a consistent form across the dataset with a distinctive curve, the 9-digit can be expressed in a variety of ways, some of which may resemble the traces of other digits (e.g., 4 or 3), making it more challenging to classify.
