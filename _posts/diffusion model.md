---
title: 'Diffusion model'
date: 2024-09-01
permalink: /posts/2024/09/blog-post-1/
tags:
  - generative AI
  - diffusion model
  - text to image
---

It is said that the best way to learn something is to do it and explain it to others in my own language.

One thing that I learned from the author of diffusion policy is that the it can handle data with multi modality.

Then I have a question about what is multi modality in data.

# Multi-modality
real data are often multimodal.


# What is diffusion model?

## Mathematical explanation
One question I used to have for diffusion model is
why the forward SDE has the form
```math
dx = h(x,t)dt+g(t)dw_t
```
where $h(x,t) is the drift coefficient, $g(t)$ is the diffusion coefficient.
while the backward SDE becomes
```math
dx = [h(x,t)-g(t)^2\Delta \log p_t(x)]dt+g(t)d\bar{w}_t
```
Where this extra term comes from.
After this semester, I got the answer. Things obvisous to other may not be obvious to me.



## Development
DDPM, DDIM acceleration.

# Applications
## text to image model


## image to image


## inpainting

## diffusion policy
Diffusion policy is first proposed in [].
It solves the problem of original imition learning which can not handle multimodal data.

# Reference
