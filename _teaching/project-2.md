---
title: "UniDA3D: Unified Domain Adaptive 3D Semantic Segmentation Pipeline"
excerpt: "This project aims to tackle several adaptation tasks in 3D segmentation field, by designing a unified source-and-target active sampling strategy to select a maximally-informative subset from both source and target domains for effective model adaptation."
collection: teaching
permalink: /teaching/project-2
venue: "How to deploy the segmentation model to another dataset"
date: 2023-01-15
location: "UniDA3D"
---

# Introduction
State-of-the-art 3D semantic segmentation models are trained on off-the-shelf public benchmarks, but they will inevitably face the challenge of recognition accuracy drop when these well-trained models are deployed to a new domain. In this paper, we introduce a Unified Domain Adaptive 3D semantic segmentation pipeline (UniDA3D) to enhance the weak generalization ability, and bridge the point distribution gap between domains. Different from previous studies that only focus on a single adaptation task, UniDA3D can tackle several adaptation tasks in 3D segmentation field, by designing a unified source-and-target active sampling strategy, which selects a maximally-informative subset from both source and target domains for effective model adaptation. Besides, benefiting from the rise of multi-modal 2D-3D datasets, UniDA3D investigates the possibility of achieving a multi-modal sampling strategy, by developing a cross-modality feature interaction module that can extract a representative pair of image and point features to achieve a bi-directional image-point feature interaction for safe model adaptation. Experimentally, UniDA3D is verified to be effective in many adaptation tasks including: 1) unsupervised domain adaptation, 2) unsupervised few-shot domain adaptation; 3) active domain adaptation. Their results demonstrate that, by easily coupling UniDA3D with off-the-shelf 3D segmentation baselines, domain generalization ability of these baselines can be enhanced.


# Some Visualization Results

[Multi-dataset prediction:](https://arxiv.org/abs/2212.10390)

Here, we give some visualization examples to show how to achieve a unified domain adaptive baseline for 3D semantic segmentation task.

<p align="center">
    <img  src="../images/seq_demo_once.gif" width="70%">
</p>

<p align="center">
<img src="../images/seq_demo_nusc.gif" width="70%">
</p>