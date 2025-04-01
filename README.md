# Diffusion-Model-4-Quark-Gluon-Events

## Summary
+ When handling physics-based dataset imagery rather than standard RGB images, preprocessing requires special attention to preserve essential physical attributes. In our experiment, careful pixel value scaling was essential to maintain critical image features.

+ While metrics such as SSIM and PSNR could theoretically evaluate the comparison between original and reconstructed events, our backward process failed to produce meaningful representations.

+ We found beta scheduler selection to be a key factor in our process. Through manual image inspection, we implemented a linear beta schedule with customized start and end values.

+ Additional research and refinement are necessary to develop effective diffusion models for image-based physical quark/gluon data. Future work should investigate varied diffusion schedules, preprocessing approaches, and model architectures better suited to capturing the data's underlying physical characteristics.

## References
Diffusion paper: https://arxiv.org/pdf/2006.11239
https://www.kaggle.com/code/vikramsandu/ddpm-from-scratch-in-pytorch
https://medium.com/@brianpulfer/enerating-images-with-ddpms-a-pytorch-implementation-cef5a2ba8cb1
