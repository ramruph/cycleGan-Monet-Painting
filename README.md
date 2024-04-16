# Monet CycleGAN project


## Description of problem
Generate images in the style of Monet. This generator is trained using a discriminator.The two models will work against each other, with the generator trying to trick the discriminator, and the discriminator trying to accurately classify the real vs. generated images.

My task is to build a GAN that generates 7,000 to 10,000 Monet-style images.

I will utilize the tensorflow library and utlizie their documentations such as tutorial for implementing CycleGans to Horses images and other code documentations


### Kaggle Evaluation -> MiFID
Submissions are evaluated on MiFID (Memorization-informed Fréchet Inception Distance), which is a modification from Fréchet Inception Distance (FID).

The smaller MiFID is, the better the generated images is.



## Data Description
The monet directories contain Monet paintings. I use these images to train my model.

The photo directories contain photos. Add Monet-style to these images and submit your generated jpeg images as a zip file

Files:
- monet_jpg - 300 Monet paintings sized 256x256 in JPEG format
- monet_tfrec - 300 Monet paintings sized 256x256 in TFRecord format
- photo_jpg - 7028 photos sized 256x256 in JPEG format
- photo_tfrec - 7028 photos sized 256x256 in TFRecord format



# EDA
- Size images to 256x256. 
- As these images are RGB images, set the channel to 3. 
- Scale the images to a [-1, 1]


# Model & Analysis (model building and training) 
- To design the cycleGAN I need to construct two generators:
    - upsampling : filters 2d dims by a defined stride
    - downsampling: increases 2d dims by a defined stride
- "The generator first downsamples the input image and then upsample while establishing long skip connections. Skip connections are a way to help bypass the vanishing gradient problem by concatenating the output of a layer to multiple layers instead of only one. Here we concatenate the output of the downsample layer to the upsample layer in a symmetrical fashion" - Amy Jang
- Desgin Generator to create Monet Images and Discriminator to determine accuracy of generated images. Both would utilize sampling techniques
  
### Model Parameters
HEIGHT = 256
WIDTH = 256
CHANNELS = 3
EPOCHS = 50
BATCH_SIZE = 1

# Results

insert image of results here

