---
title: 'Flow matching is a controllability problem'
date: 2025-05-15
permalink: /posts/2024/09/blog-post-1/
tags:
  - generative AI
  - diffusion model
  - text to image
---
# Introduction
At the Spring 2025 semester, I took the class **Optimal transport** and a special problem related to **Schrondinger bridge over averaged systems** taught by Professor Yongxin Chen at Gerogia Tech.
I am a curious person but not smart. I admire those researchers know how to use what they learned to apply it to many applications, like large language model (LLM), generative AI and so on.
My post here is to help me understand things better and connect different things.

After a short internship in a company and talking to different collegues about the projects they are doing, the curiosity of how the diffusion model and flow matching things work grows bigger and bigger.

I start to do projects in simple systems (not big dataset of images, text, or audio). I like understanding things from the basic theory instead of waiting for the computer or GPU to return me some image generation results.
# Stochastic optimal control and Schrondinger bridge problem
In class, Professor mentioned this popular flow matching conception in industry is just a special case in stochastic optimal control (SOC)/Shcrodinger bridge (SB) problem when the system dynamics is quite simple form.

There are many intersting problems in SOC and SB, and the solution to them are only for some linear quadratic form.
I will cover this part in my future research as I learn more.

# Flow matching
So I start to do the project of using flow matching... (I will talk about it after the paper is published.)
The Professor I am cooperating with told me **flow matching is a controllability problem**. This is when I start to connect flow matching with control.
My understanding of flow matching is to learn a velocity field $u$ from intial distribution and target distribution using neural networks.
This $u$ is modeled as $u(t)=F(x_t,t)$ where $F$ is a funtional family like neural network or what ever basis function you want to use. 
To deviate a little bit from the topic, there is a very famous mathematician giving a talk about neural network and its connection to math/physics and I think his talk basically covered everythin about how researchers use neural network to learn representations.

## what is flow matching
Flow matching is a very popular method proposed by Meta researchers [].
The basic idea of flow matching is.

# Controllability
Let's go back to the definition of controllability in control theory.
A system is controllable, if for every $x^*(t)$ and every finite $t_f>0$, there exists an input function $u(t)$ such that the system goes from $x_0$ to $x(t_f)=x^*$.

Consider a continuous linear system
```math
\dot x(t) = A(t)x(t)+B(t)u(t) \\
y(t) = C(t)x(t)+D(t)u(t)
```
There exists a control $u$ from state $x_0$ at time $t_0$ to state $x_1$ at time $t_1>t_0$ iff $x_1-\phi(t_0,t_1)x_0$ is in the column space of the controllability Gramian
```math
W(t_0,t_1) = \int_{t_0}^{t_1}\phi(t_0, t)B(t)B(t)^\top \phi(t_0,t)^\top dt
``` 
The $u$ that can achive this transfer from $x_0$ and $x_1$ is given by the
```math
u(t) = -B(t)^\top \phi(t_0,t)^\top \eta_0
```
where $\eta_0$  satisfies $W(t_0,t_1)\eta=x_1-\phi(t_0,t_1)x_0$.

For conitnuous linear time-invariant systems
```math
\dot x(t)=Ax(t)+Bu(t) \\
y(t) = Cx(t)+Du(t)
```
The system is contollable if the controllability matrix $R=[B,AB,A^2B,\dots A^{n-1}B]$ has full rank.


# Can flow matching drive every initial distribution to a target distribution?
Yes, if the system is controllable and the test data has the same support as the training data.


# Can flow matching handle out of distribution data?
When I run the flow matching code, I found that if I fix the initial distribution and target distribution, and train  the velocity field.
Then I can use this trained velocity field for any initial distribution and drive it to the same target distribution.
Why?
What if the test set is using a sample initial distribtion quite different from the initial one or out of range of the intial one?
When I set $\mu_0=\mu_f$, the algorithm fail, I guess that's because $u=0$ and my simulation says I am correct, yeeee!

# About the jaggy/nonsmooth learned velocity field.
Why? My first intuition is that since flow matching is doing linear interpretation between states, it is normal that the learned $u(x)$ is like piecewise.
Is that true. Still trying to figure it out.

# Examples
I use the code from the library [] and test different initial and target distribution.
## Gaussian to gaussian


## HalfMoon to circle

## Gaussian to HalfMoon


## Generalization to different support
I don't think it can generalize to data set with different support from that of the initial distribution based on my understanding.
## add noise to the velocity field
I also notice a high sensitivity to noise of using flow matching.
If I add noise to the learned velocity field, it can not drive the initial distribution to the target anymore.

# Code
Here is the code for the examples. Please let me know if you find any bugs and would love to contribute to the repo.

# Reference
- [1] 
- [2] 
- [3] https://en.wikipedia.org/wiki/Controllability#:~:text=Roughly%2C%20the%20concept%20of%20controllability,the%20type%20of%20models%20applied.
- [4]
- [5]
- [6]
- [7]
- [8]
- [9]
- [10]








