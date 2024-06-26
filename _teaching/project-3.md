---
title: "3DTrans Codebase Introduction"
excerpt: "An Open-source Codebase for exploring Continuous-learning/Pre-training-oriented Autonomous Driving Task"
collection: teaching
permalink: /teaching/project-3
venue: "The first codebase for 3D pre-training and continuous learning"
date: 2023-03-15
location: "3DTrans"
---

<p align="center">
    <img  src="../images/seq_demo_once.gif" width="70%">
</p>

<p align="center">
<img src="../images/seq_demo_nusc.gif" width="70%">
</p>

## Overall

This blog will introduce the 3DTrans codebase developed by ADLab Team, which supports 3D point cloud transfer learning under autonomous driving for the first time. Besdies, 3DTrans codebase is also the official implementation codebase of Uni3D (accepted by CVPR-2023) and Bi3D (accepted by CVPR-2023).

---

## **What does 3DTrans Codebase do?**

**1) Rapid Target-domain Adaptation:** `3DTrans` can boost the 3D perception model's adaptability for an unseen domain only using unlabeled data. For example, [ST3D](https://arxiv.org/abs/2103.05346) supported by `3DTrans` repository achieves a new state-of-the-art model transfer performance for many adaptation tasks, further boosting the transferability of detection models. Besides, `3DTrans` develops many new UDA techniques to solve different types of domain shifts (such as LiDAR-induced shifts or object-size-induced shifts), which includes Pre-SN, Post-SN, and range-map downsampling retraining.

**2) Annotation-saving Target-domain Transfer:** `3DTrans` can select the most informative subset of an unseen domain and label them at a minimum cost. For example, `3DTrans` develops the [Bi3D](https://arxiv.org/abs/2303.05886), which selects partial-yet-important target data and labels them at a minimum cost, to achieve a good trade-off between high performance and low annotation cost. Besides, `3DTrans` has integrated several typical transfer learning techniques into the 3D object detection pipeline. For example, we integrate the [TQS](https://openaccess.thecvf.com/content/CVPR2021/papers/Fu_Transferable_Query_Selection_for_Active_Domain_Adaptation_CVPR_2021_paper.pdf), [CLUE](https://arxiv.org/abs/2010.08666), [SN](https://arxiv.org/abs/2005.08139), [ST3D](https://arxiv.org/abs/2103.05346), [Pseudo-labeling](https://arxiv.org/abs/2103.05346), [SESS](https://arxiv.org/abs/1912.11803), and [Mean-Teacher](https://arxiv.org/abs/1703.01780) for supporting autonomous driving-related model transfer.

**3) Joint Training on Multiple 3D Datasets:** `3DTrans` can perform the multi-dataset 3D object detection task. For example, `3DTrans` develops the [Uni3D](https://arxiv.org/abs/2303.06880) for multi-dataset 3D object detection, which enables the current 3D baseline models to effectively learn from multiple off-the-shelf 3D datasets, boosting the reusability of 3D data from different autonomous driving manufacturers.

**4) Multi-dataset Support:** `3DTrans` provides a unified interface of dataloader, data augmentor, and data processor for multiple public benchmarks, including Waymo, nuScenes, ONCE, Lyft, and KITTI, etc, which is beneficial to study the transferability and generality of 3D perception models among different datasets. Besides, in order to eliminate the domain gaps between different manufacturers and obtain generalizable representations, `3DTrans` has integrated typical unlabeled pre-training techniques for giving a better parameter initialization of the current 3D baseline models. For example, we integrate the [PointContrast](https://arxiv.org/abs/2007.10985) and [SESS](https://arxiv.org/abs/1912.11803) to support point cloud-based pre-training task.

**5) Extensibility for Multiple Models**: `3DTrans` makes the baseline model have the ability of cross-domain/dataset safe transfer and multi-dataset joint training. Without making major changes of the code and 3D model structure, a single-dataset 3D baseline model can be successfully adapted to an unseen domain or dataset by using our `3DTrans`.

<p align="center">
  <img src="../images/3DTrans_1.png" width="90%">
</p>

## **Introduction for Each Module**

`3DTrans` is a lightweight, simple, self-contained open-source codebase for exploring the **Autonomous Driving-oriented Transfer Learning Techniques**, which mainly consists of **four** functions at present:

1) Unsupervised Domain Adaptation (UDA) for 3D Point Clouds

2) Active Domain Adaptation (ADA) for 3D Point Clouds

3) Semi-Supervised Domain Adaptation (SSDA) for 3D Point Clouds

4) Multi-dateset Domain Fusion (MDF) for 3D Point Clouds

---

- Code Link:
    
    [https://github.com/PJLab-ADG/3DTrans/blob/master/docs/GETTING_STARTED_UDA.md](https://github.com/PJLab-ADG/3DTrans/blob/master/docs/GETTING_STARTED_UDA.md)
    

- **UDA Module Introduction**

`3DTrans`  is a codebase for supporting transfer learning in autonomous driving, and the most common transfer learning task is the UDA task. The assumption in UDA task is that the model can access to a full amount of labeled source domain data and unlabeled target domain data. `3DTrans`  achieves the existing UDA 3D methods such as ST3D[1]. Similarly, we provide LiDAR down-sampling retraining and Post/Pre-SN implementations for two common domain differences in 3D autonomous driving scenarios, namely, LiDAR-beam variation and Object-size change, to reduce target-specific domain differences.

- **UDA@3DTrans, Experimental Results:**


<p align="center">
  <img src="../images/3DTrans_2.png" width="90%">
</p>

---

- Code Link:
    
    [https://github.com/PJLab-ADG/3DTrans/blob/master/docs/GETTING_STARTED_ADA.md](https://github.com/PJLab-ADG/3DTrans/blob/master/docs/GETTING_STARTED_ADA.md)
    

- **ADA Module Introduction**

`3DTrans` codebase supports a variety of typical ADA algorithms for the first time, including TQS[2], CLUE[3] and our Bi3D. Besides, by means of the TQS in `3DTrans`, you can perform well the query-by-committee, uncertainty, and other ADA evaluation metrics.

TQS [2] consists of transferable committee, transferable uncertainty and transferable domain based on image-level features. In our reproduction, we use CNN to extract scene-level feature descriptions from BEV features, and use three classifier heads to build committees. Different from previous work using entropy to assess uncertainty, we calculated objective scores and a flag of 0.5. This scoring method is different from the original TQS [2] because we only focus on a single category and cannot use the highest score and The second highest score difference. Furthermore, we compute the domain score by the domain discriminator and set theta=0.75, delta=0.4, which is the same as TQS. To be consistent with TQS, we use source domain data and selected target data to fine-tune the detector trained on the source domain

CLUE [3] uses uncertainty weighted clustering to select target data. Following this idea, we first obtain the uncertainty per frame by calculating the predicted entropy after NMS, and then use the average value of the entropy to represent the frame-level uncertainty. In addition, weighted K-Means and K centers proposed by CLUE [3] are used for clustering, where K represents the labeling budget at the current sampling moment.

- **ADA@3DTrans, Experimental Results:**

<p align="center">
  <img src="../images/3DTrans_3.png" width="90%">
</p>

---

- Code Link:
    
    [https://github.com/PJLab-ADG/3DTrans/blob/master/docs/GETTING_STARTED_SSDA.md](https://github.com/PJLab-ADG/3DTrans/blob/master/docs/GETTING_STARTED_SSDA.md)
    

- **SSDA Module Introduction**

`3DTrans` codebase also supports a variety of semi-supervised algorithms, including the classic SESS[5] and Pseudo-Label[6] algorithms. And we show how to use the above semi-supervised method to deploy the model to the target domain under the domain shifts. The technical route of SSDA is: source domain pre-training model -> fine-tuning under 1% or 5% labeled target domain data -> retraining under semi-supervised target domain data. The semi-supervised algorithms supported by `3DTrans` are as follows:

SESS[5] is an algorithm that guides the teacher model and the student model to randomly perturb the input data to maintain prediction consistency under the Mean Teacher paradigm. It designs a specific point-based data perturbation scheme and three consistency losses, which enable the network to generate more accurate detections. We have reproduced SESS in the code base and applied it to cross-domain detection.

- **SSDA@3DTrans, Experimental Results:**

<p align="center">
  <img src="../images/3DTrans_4.png" width="90%">
</p>

---

- Code Link:
    
    [https://github.com/PJLab-ADG/3DTrans/blob/master/docs/GETTING_STARTED_MDF.md](https://github.com/PJLab-ADG/3DTrans/blob/master/docs/GETTING_STARTED_MDF.md)
    

- **MDF Module Introduction**

`3DTrans` codebase supports MDF task setting in 3D scene for the first time. Multi-domain Dataset Fusion (MDF) refers to the joint training of 3D object detectors on multiple datasets, which is necessary to achieve high detection accuracy from multiple datasets at the same time. It should be noted that compared with the Multi-source Domain Adaptation in the Domain Adaptation (DA) field, the MDF task proposed here does not require a close-set relationship assumption between different domains, which means that, from different domains (or datasets), the category distribution from different domains can be inconsistent. Compared with Multi-source Domain Adaptation, MDF task setting relaxes the conditional restrictions on data distribution and category distribution between different domains.

- **MDF@3DTrans, Experimental Results:**

<p align="center">
  <img src="../images/3DTrans_5.png" width="90%">
</p>

---

---

- Code Link:
    
    [https://github.com/PJLab-ADG/3DTrans/blob/master/docs/QUICK_SEQUENCE_DEMO.md](https://github.com/PJLab-ADG/3DTrans/blob/master/docs/QUICK_SEQUENCE_DEMO.md)
    

- **Visualization Module Introduction**

At present, the visualization modules of some existing 3D point cloud code libraries are all single-frame visualizations, which lack processing for time-series data. To this end, we have added a Sequence-level visual UI tool to the `3DTrans`  codebase, and the visualization effect is very intuitive. Currently, it mainly supports the visualization of timing detection results of Waymo, ONCE and nuScenes datasets. The user can give a sequence ID to generate the corresponding visual content.

![Untitled](../images/3DTrans_1.gif)


## What `3DTrans` is Doing

The recent ChatGPT / GPT-4 and other large language models have inspired us that we should think about the large-scale point cloud dataset pre-training under the autonomous driving. As we all know, a comprehensive and diverse corpus is the major reason of building a powerful or general-purpose NLP large model. Some research studies have shown that, if representative and highly differentiated pre-training datasets can be obtained, the increase in the number of basic model parameters can lead to an improvement in downstream performance.

However, in the 3D LiDAR autonomous driving scenario, due to the large differences between the raw data provided by different manufacturers, it is difficult to obtain a unified dataset in the field of autonomous driving. Therefore, at this stage, we believe that a necessary route to achieve unified perception in the field of autonomous driving is to construct a unified dataset, or to design a unified baseline model so that it can learn a unified representation in a differentiated dataset. Of course, Uni3D chose the latter route. At the same time, we also tried to achieve the former route. Bi3D is exploring how to select the most valuable data from the massive unlabeled autonomous driving data set. .

**Recently, we are exploring the effective algorithms to select valuable samples (diversity and low redundancy) from massive autonomous driving scenes, and further designing effective solutions to allow models to learn unified representations from multi-source data.**


## Reference

[1] Jihan Yang, Shaoshuai Shi, Zhe Wang, Hongsheng Li, Xiaojuan Qi. ST3D: Self-training for Unsupervised Domain Adaptation on 3D Object Detection.

[2] Bo Fu, Zhangjie Cao, Jianmin Wang, and Mingsheng Long. Transferable Query Selection for Active Domain Adaptation.

[3] Viraj Prabhu, Arjun Chandrasekaran, Kate Saenko, Judy Hoffman. Active Domain Adaptation via Clustering Uncertainty-weighted Embeddings.

[4] Yan Wang, Xiangyu Chen, Yurong You, Li Erran, Bharath Hariharan, Mark Campbell, Kilian Q. Weinberger, Wei-Lun Chao. Train in Germany, Test in The USA: Making 3D Object Detectors Generalize.

[5] Na Zhao, Tat-Seng Chua, Gim Hee Lee. SESS: Self-Ensembling Semi-Supervised 3D Object Detection.

[6] Antti Tarvainen, Harri Valpola. Mean teachers are better role models: Weight-averaged consistency targets improve semi-supervised deep learning results.

[7] Saining Xie, Jiatao Gu, Demi Guo, Charles R. Qi, Leonidas J. Guibas, Or Litany. PointContrast: Unsupervised Pre-training for 3D Point Cloud Understanding