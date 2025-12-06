**Hybrid CNN-ViT for Image Classification (CIFAR-100)**

This repository contains an implementation of a Hybrid Convolutional Neural Network + Vision Transformer (CNN-ViT) model designed to combine the strengths of both architectures. The goal of this project was to improve classification accuracy on CIFAR-100 by using an adaptive fusion mechanism instead of relying on a single model type.

**Project Overview**

Traditional CNNs (like ConvNeXt-style models) are great at capturing local spatial features, while Vision Transformers are strong at modeling global dependencies.
In this project, I combine both branches and use a learnable gating module to fuse their features adaptively during training.

**The model includes:**

A CNN feature extractor (ConvNeXt-V2 inspired).

A Vision Transformer (ViT) branch.

A gating fusion module that learns how much weight to assign to CNN vs. ViT features.

A final classifier head.

This allows the model to decide when local details matter more and when global context is more important.

**Key Features**

Adaptive feature fusion using a gating network

Weighted fusion:
fused = w_cnn · f_cnn + w_vit · f_vit

Mixed-precision training with AMP

Trained on CIFAR-100

Baseline models included for comparison:

CNN baseline

ViT baseline

**Results Summary**
Model	Top-1 Accuracy	Notes
CNN Baseline	83.03%	Shows signs of overfitting after 10 epochs
ViT Baseline	82.50%	Also overfits but slightly weaker than CNN
Hybrid CNN-ViT (ours)	Significantly improved performance	Benefits from adaptive fusion

