---
title: "Multi-dataset 3D Object Detection"
excerpt: "This project aims to find a unified model structure to enable the existing 3D object detection models to learn from different 3D datasets."
collection: portfolio
---

# Introduction
Current 3D object detection models follow a single dataset-specific training and testing paradigm, which often faces a serious detection accuracy drop when they are directly deployed in another dataset. In this paper, we
study the task of training a unified 3D detector from multiple datasets. We observe that this appears to be a challenging task, which is mainly due to that these datasets present substantial data-level differences and taxonomylevel variations caused by different LiDAR types and data acquisition standards. Inspired by such observation, we present a Uni3D which leverages a simple data-level correction operation and a designed semantic-level couplingand-recoupling module to alleviate the unavoidable datalevel and taxonomy-level differences, respectively. Our method is simple and easily combined with many 3D object detection baselines such as PV-RCNN and Voxel-RCNN,
enabling them to effectively learn from multiple off-theshelf 3D datasets to obtain more discriminative and generalizable representations. Experiments are conducted on many dataset consolidation settings including WaymonuScenes, nuScenes-KITTI, Waymo-KITTI, and WaymonuScenes-KITTI consolidations. Their results demonstrate that Uni3D exceeds a series of individual detectors trained
on a single dataset, with a 1.04× parameter increase over a selected baseline detector. We expect this work will inspire the research of 3D generalization since it will push the limits of perceptual performance

# Some Visualization Results

[Multi-dataset prediction:](https://arxiv.org/abs/2303.06880)

Here, we show the sequence-level visualization results by our codebase.

<iframe  src="../images/seq_demo_waymo_bev.gif" width="70%">
<iframe  src="../images/seq_demo_waymo_fp.gif" width="70%">