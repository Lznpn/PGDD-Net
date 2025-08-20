<div align="center">


<h1>PGDD-Net: Unified Unsupervised Deepfake Detection with Prototype Guidance and Dual-DeepSVDD</h1>

</div>  <!-- ✅ 这一行必须加，结束居中区域 -->

## ⭐ Abstract

Although Deepfake technology holds promise in media and entertainment, its malicious use for fraud and defamation poses serious threats to social stability and public trust. Most existing Deepfake detection methods rely heavily on extensive labeled training data, which is costly and resourceintensive to acquire. Moreover, existing unsupervised detection approaches suffer from feature-decision decoupling, limiting their generalization capability. To address these fundamental limitations, we propose a unified unsupervised framework named PGDD-Net, which integrates feature learning with geometric decision-making without requiring labeled data. First, we design a novel pseudo-label generation method based on visual artifact features that provides reliable supervisory signals for unlabeled training samples. Then, we propose a Prototype-Guided Contrastive Learning (PGCL) that enhances discriminative capability through momentum-updated class prototypes, which promotes intra-class compactness and enhances inter-class separability for effective feature learning. Finally, we design Dual Deep Support Vector Data Description (Dual-DeepSVDD) to effectively integrate discriminative feature learning and geometric decisionmaking by constructing dual hyperspheres for real and fake samples. The effectiveness of the method is validated on four benchmark datasets, including FF++, DFDC, DFR, and CelebDF. Extensive experimental results show that the method achieves the best performance among unsupervised methods while remaining competitive with supervised approaches, demonstrating its potential for practical applications.

## 📑 Overview Comparison

<div align="center">
    <img width="550" alt="image" src="Image\1.png">
</div>


The figure shows the comparison of mainstream unsupervised deepfake detection methods. Our proposed unified framework effectively integrates feature learning and decision-making processes through dual hypersphere modeling, which achieves significantly better generalization performance across different datasets.

## 📻 Overview

<div align="center">
    <img width="700" alt="image" src="Image\2.png">
</div>


<div align="center">
Illustration of the overall architecture.
</div>
## 📆 TODO LIST

- [x] Project page released
- [x] Dataset preparation instructions released
- [ ] Release of core codes
- [ ] Release the complete model code

## 🖥️ How to Use

### 1. Install Environment

```python
cd PGDD-Net
conda create -n PGDD python=3.8.19
conda activate PGDD
pip install -r requirements.txt
```

### 2. Dataset Preparation

We share the <a href="https://mmlab.ie.cuhk.edu.hk/projects/CelebA.html" style="color:#0078d4;">FF++</a>, <a href="https://github.com/yuezunli/celeb-deepfakeforensics" style="color:#0078d4;">Celeb-DF</a>, <a href="https://liming-jiang.com/projects/DrF1/DrF1.html" style="color:#0078d4;">DFR</a>, <a href="https://ai.meta.com/datasets/dfdc" style="color:#0078d4;">DFDC</a>, which be downloaded through this link. Please use MTCNN crop the face area, sample 20 frames from each video.

### 3. Train

#### Stage 1: Pseudo-labels Generation

```python
python vaf_pseudo_labeler.py
```

#### Stage 2: Prototype-Guided Contrastive Learning

```python
python pgcl_train.py
```

#### Stage 3: Dual Deep Support Vector Data Description

```python
python deepsvdd_train.py
```

### 4. Test

```
python test.py
```

## 🖼️   Visualization

<div align="center">
    <img width="1000" alt="image" src="Image\3.png">
</div>
<div align="center">
Grad-CAM visualization comparison showing attention heatmaps of different Deepfake detection methods.
</div>

## 📬 Contact

If you have any questions, please contact:

- 📧 107552304059@stu.xju.edu.cn  

  
