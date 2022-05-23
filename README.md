# Anime-Faces-Generation
Generating anime faces using a custom DCGAN
## Dataset
- A dataset from kaggle, link [here](https://www.kaggle.com/datasets/soumikrakshit/anime-faces)
-  Original dataset images

![oringinal_dataset](https://user-images.githubusercontent.com/50806086/169807087-a1870f31-3901-4d79-a327-f00d0c7e9857.png)
- Pixel values of the each image are scalled to [-1,1]

## Model
### Generator
A 128-dimensional noise vector, followed by Dense layer of `4*4*1024`, reshaped to `(4, 4, 1024)` followed by convolution transposes resulting in an image of dimensions `(64, 64, 3)` with pixel values of range [-1, 1] by tanh activation.


![generator](https://user-images.githubusercontent.com/50806086/169802605-e69b015e-1fb4-402a-9a60-2b618eee9daf.png)

### Discriminator
Discriminator acts similar to critic to output the probability of the image being real.

![discriminator](https://user-images.githubusercontent.com/50806086/169808020-4b720c78-626a-4fa3-a89b-56f68cd16903.png)


## Progress
- Each train{} is 50 epochs
### Train-1
![anime-dcgan-david-train-1](https://user-images.githubusercontent.com/50806086/169808622-71eeae42-e585-458f-b492-2f96f176a41e.gif)


### Train-2
- Used checkpoints from Train-1


![anime-dcgan-david-train-2](https://user-images.githubusercontent.com/50806086/169808679-67027b85-9365-4c8c-8467-0c30e06e6463.gif)

### Train-3
- Used checkpoints from Train-3


![anime-dcgan-david-train-3](https://user-images.githubusercontent.com/50806086/169812954-8d5c30c9-d281-4614-bd1e-7950b3793bd8.gif)

> Observe the improvement in each train step
## Environment
- The models are trained entirely on different consecutive gpu instances of google colab powered by 1 Tesla T4 each instance


### 🚀 The trained checkpoints are stored [here](https://drive.google.com/drive/folders/1Qe06jPHH1CeCmOwBn0lr8k49x6xaEMGj?usp=sharing), they can be restored as suggested in the notebook
## Acknowledgments 
- Inspired from [this repo](https://github.com/yashyenugu/Anime-Face-GAN)
- Resources used:
  -  Original DCGAN paper [abstract](https://arxiv.org/abs/1511.06434)
  -  Tensorflow tutorial [colab](https://www.tensorflow.org/tutorials/generative/dcgan)
