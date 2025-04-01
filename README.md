# Diffusion-Model-for-Quark-Gluon-Events

## Summary

Our code implements diffusion model for generating jet images. The architecture here we used is Denoising Diffusion Probabilistic Model (DDPM) with a U-Net backbone that learns to reverse a noise-adding process. The dataset consists of jet images with three channels (track, ECAL, and HCAL), which are preprocessed, normalized, and resized before being fed into the model.
The core architecture consists of:

+ A U-Net with downsampling and upsampling blocks
+ Sinusoidal time embeddings to condition the model on diffusion timesteps
+ Residual connections between corresponding layers
+ A forward diffusion process that gradually adds noise to images
+ A reverse diffusion process that removes noise step by step

The training loop runs for 20 epochs, where at each step it applies random noise to images, asks the model to predict that noise, and uses L1 loss to optimize. The model generates new images by starting from pure noise and iteratively denoising through all timesteps. We include visualizations to show both the forward noising process and the reverse generation process, allowing us to monitor model's progress throughout training.

### Datset Image

<img src="./assets/Diffusion Model Notebook.png">

## Results

+ While metrics such as SSIM and PSNR could theoretically evaluate the comparison between original and reconstructed events, our backward process failed to produce meaningful representations.

+ When handling physics-based dataset imagery rather than standard RGB images, preprocessing requires special attention to preserve essential physical attributes. In our experiment, careful pixel value scaling was essential to maintain critical image features.

+ We found beta scheduler selection to be a key factor in our process. Through manual image inspection, we implemented a linear beta schedule with customized start and end values.

+ Additional research and refinement are necessary to develop effective diffusion models for image-based physical quark/gluon data. Future work should investigate varied diffusion schedules, preprocessing approaches, and model architectures better suited to capturing the data's underlying physical characteristics.

## References
Diffusion paper: https://arxiv.org/pdf/2006.11239
https://www.kaggle.com/code/vikramsandu/ddpm-from-scratch-in-pytorch
https://medium.com/@brianpulfer/enerating-images-with-ddpms-a-pytorch-implementation-cef5a2ba8cb1
