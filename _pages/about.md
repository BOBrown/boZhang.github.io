---
permalink: /
title: "Bo Zhang"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Researcher & Shanghai AI Laboratory.

**Office**: Level 12, L1, Longwen Road No. 129, Xuhui District, Shanghai, China

**Email**: zhangbo [at] pjlab.org.cn & bo.zhangzx [at] gmail.com

**Academic activities**: Reviewer at CVPR/ECCV/ICCV/ICML/ICLR/ACM-MM & T-PAMI/TIP/TGRS/T-CSVT/T-MM/T-NNLS/TKDE

Bo Zhang received the Ph.D. degree in electronic engineering from Fudan University, in 2022. His research is focused on 3D multi-modal complicated reasoning task, including multi-modal structural representation learning, 2D/3D pre-training, 2D/3D continuous learning. 

His work has led to many awards, including **Shanghai Rising Star** under Grant No. 23QD1401000, awarded by the Shanghai Municipal Commission of Science and Technology, the National Scholarship 2021 China Award, the 2019 Excellent Doctoral Scholarship of Fudan University Award, and various awards from VALSE China and Shanghai Government. His research outcomes have some impacts on industrial applications like airport checkpoint security perceptual recognition and localization of concealed or dangerous objects. 

He is currently a Researcher with Shanghai AI Laboratory, working on developing many major open-source projects including: 1) **Open-source codebase of 3D pre-training task** ([3DTrans Code Link](https://github.com/PJLab-ADG/3DTrans)); 2) **Open-source codebase of multi-modal complicated reasoning task**


<!-- ***We are hiring***: Our team aims to broaden the boundaries of general perception-reasoning task, trying to find unified-yet-structured representations that can be generalized across different domains and scenarios under different modalities and tasks. Meanwhile, we are working on extracting knowledge-rich data from different domains. We are searching for highly self-motivated interns. If you are interested in our research tpoic, do not hesitate to contact me. -->

# News
---
- May 16, 2024, Not All Experts are Equal: Efficient Expert Pruning and Skipping for Mixture-of-Experts Large Language Models ([arXiv paper](https://arxiv.org/abs/2402.14800)) is accepted by **ACL 2024**.
- May 02, 2024, Cross-Task Linearity Emerges in the Pretraining-Finetuning Paradigm ([arXiv paper](https://arxiv.org/abs/2402.03660)) is accepted for publication in **ICML 2024**.
- Feb 28, 2024, Our paper entitled "Once for Both: Single Stage of Importance and Sparsity Search for Vision Transformer Compression" ([arXiv paper](https://arxiv.org/abs/2403.15835)) is accepted for publication in **CVPR 2024**.
- Jan 15, 2024, Our paper entitled "ReSimAD: Zero-Shot 3D Domain Transfer for Autonomous Driving with Source Reconstruction and Target Simulation" ([arXiv paper](https://arxiv.org/abs/2309.05527)) is accepted for publication in **ICLR 2024**.
- Jan 02, 2024, **Two papers** are accepted by TCSVT: [IPNet](https://ieeexplore.ieee.org/abstract/document/10516600), [MVNet](https://ieeexplore.ieee.org/abstract/document/10360874).
- Sep 24, 2023, StructChart, our research on visual chart, has been released ([arXiv paper](https://arxiv.org/abs/2309.11268)), where we will release the SimChart9K dataset powered by LLM. By the proposed SimChart9K, we observe that StructChart continuously improves the chart perception performance as more simulated charts are used for pre-training.
- Sep 29, 2023, SPOT, showing a promising and **scalable** 3D pre-training on autonomous driving, has been released (See our paper for more details, [arXiv paper](https://arxiv.org/abs/2309.10527)).
- Sep 22, 2023, One paper entitled “AD-PT: Autonomous Driving Pre-Training with Large-scale Point Cloud Dataset” is accepted by **NeurIPS-2023**.
- Aug 16, 2023, One paper about cross-domain background-fouced alignment "Rethinking Cross-Domain Pedestrian Detection: A Background-Focused Distribution Alignment Framework for Instance-Free One-Stage Detectors" is accepted by **TIP**.
- Jul 20, 2023, One paper entitled "SUG: Single-dataset Unified Generalization for 3D Point Cloud Classification" is accepted by **ACM MM-2023**.
- May 25, 2023, AD-PT, our research on **3D point-cloud pre-training**, has been released ([Code](https://github.com/PJLab-ADG/3DTrans), [arXiv paper](https://arxiv.org/abs/2306.00612)).
- Apr 10, 2023, One paper entitled "Performance-aware Approximation of Global Channel Pruning for Multitask CNNs" is accepted for publication in **T-PAMI**.
- Mar 20, 2023, Bo Zhang started to work on exploring how to improve the reasoning ability of LLMs or VLMs in complex modalities, such as **Chart, Table, Geometry, Scientific Document Understanding**, by investigating foundation LLM models from the perspective of structured knowledge-rich data.
- Mar 08, 2023, **Three papers** are accepted by CVPR-2023: Uni3D, Bi3D, GDP.
- Dec 20, 2022, One paper entitled "A Closer Look at Few-Shot 3D Point Cloud Classification" is accepted for publication in **IJCV**.
- Jun 15, 2022, Bo Zhang received the Ph.D. degree in electronic engineering from Fudan University.


<br/>

# Selected Publications
---
- ^ refers to the corresponding author

**Efficient AI:**

Not All Experts are Equal: Efficient Expert Pruning and Skipping for Mixture-of-Experts Large Language Models. Xudong Lu, Qi Liu, Yuhui Xu, Aojun Zhou, Siyuan Huang, **Bo Zhang**, Junchi Yan, Hongsheng Li. <u>Published in ACL-2024.</u> ([Code](https://github.com/Lucky-Lance/Expert_Sparsity), CCF A)

Cross-Task Linearity Emerges in the Pretraining-Finetuning Paradigm. Zhanpeng Zhou, Zijun Chen, Yilan Chen, **Bo Zhang^**, Junchi Yan. <u>Published in ICML-2024.</u> ([arXiv](https://arxiv.org/pdf/2402.03660), CCF A)

Once for Both: Single Stage of Importance and Sparsity Search for Vision Transformer Compression. Hancheng Ye, Chong Yu, Peng Ye, Renqiu Xia, Yansong Tang, Jiwen Lu, Tao Chen, **Bo Zhang^**. <u>Published in CVPR-2024.</u> ([Code](https://github.com/HankYe/yolov5prune), CCF A)

Generative Diffusion Prior for Unified Image Restoration and Enhancement. Ben Fei, Zhaoyang Lyu, Liang Pan, Junzhe Zhang, Weidong Yang, Tianyue Luo, **Bo Zhang**, Bo Dai. <u>Published in CVPR-2023.</u> ([Code](https://github.com/Fayeben/GenerativeDiffusionPrior), CCF A)

Performance-aware Approximation of Global Channel Pruning for Multitask CNNs. Hancheng Ye, **Bo Zhang**, Tao Chen, Jiayuan Fan, and Bin Wang. <u>Published in T-PAMI.</u> ([Code](https://github.com/HankYe/yolov5prune), CCF A)


**Autonomous Driving and domain transfer**:

ReSimAD: Zero-Shot 3D Domain Transfer for Autonomous Driving with Source Reconstruction and Target Simulation. **Bo Zhang**, Xinyu Cai, Jiakang Yuan, Donglin Yang, Jianfei Guo, Xiangchao Yan, Renqiu Xia, Botian Shi, Min Dou, Tao Chen, Si Liu, Junchi Yan, Yu Qiao. <u>Published in ICLR-2024.</u> ([Code](https://github.com/PJLab-ADG/3DTrans#resimad), Tsinghua A)

AD-PT: Autonomous Driving Pre-Training with Large-scale Point Cloud Dataset. Jiakang Yuan, **Bo Zhang^**, Xiangchao Yan, Tao Chen, Botian Shi, Yikang LI, Yu Qiao. <u>Published in NeurIPS-2023.</u> ([Code](https://github.com/PJLab-ADG/3DTrans), CCF A)

Rethinking Cross-Domain Pedestrian Detection: A Background-Focused Distribution Alignment Framework for Instance-Free One-Stage Detectors. Yancheng Cai, **Bo Zhang**, Baopu Li, Tao Chen, Hongliang Yan, and Jiahao Xu. <u>Published in TIP.</u> (Code will be available, CCF A)

SUG: Single-dataset Unified Generalization for 3D Point Cloud Classification. Siyuan Huang, **Bo Zhang^**, Botian Shi, Peng Gao, Yikang Li, and Hongsheng Li. <u>Published in ACM-MM-2023.</u> ([Code](https://github.com/SiyuanHuang95/SUG), CCF A)

Uni3D: A Unified Baseline for Multi-dataset 3D Object Detection. **Bo Zhang**, Jiakang Yuan, Botian Shi, Tao Chen, Yikang LI, Yu Qiao. <u>Published in CVPR-2023.</u> ([Code](https://github.com/PJLab-ADG/3DTrans), CCF A)

Bi3D: Bi-domain Active Learning for Cross-domain 3D Object Detection. Jiakang Yuan, **Bo Zhang^**, Xiangchao Yan, Tao Chen, Botian Shi, Yikang LI, Yu Qiao. <u>Published in CVPR-2023.</u> ([Code](https://github.com/PJLab-ADG/3DTrans), CCF A)

A Closer Look at Few-Shot 3D Point Cloud Classification. C Ye, H Zhu, **B Zhang**, T Chen. <u>Published in IJCV.</u> (CCF A)

Learning cross-image object semantic relation in transformer for few-shot fine-grained image classification. **B Zhang**, J Yuan, B Li, T Chen, J Fan, B Shi. <u>Published in ACM-MM-2022.</u> ([Code](https://github.com/JiakangYuan/HelixFormer), CCF A)

Sample-centric feature generation for semi-supervised few-shot learning. **B Zhang**, H Ye, G Yu, B Wang, Y Wu, J Fan, T Chen. <u>Published in TIP.</u> ([Code](https://github.com/BOBrown/CCDA_LGFA), CCF A)

Joint distribution alignment via adversarial learning for domain adaptive object detection. **B Zhang**, T Chen, B Wang, R Li. <u>Published in TMM.</u> ([Code](https://github.com/BOBrown/JADF-caffe), Tsinghua-A, Accept without any changes during the first round)


# Ph.D Thesis
---

During the period of pursuing a Ph.D degree, Bo Zhang was focused on studying domain adaptive 2D object detection or semantic segmentation models, and has deep research and practical experience for the model adaptation/transfer task.

[Ph.D Thesis](https://drive.google.com/file/d/1CceNJTwc_QN6B3aE1rIscS65f4dYQdwF/view?usp=share_link)