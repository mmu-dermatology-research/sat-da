# SAT-DA Architecture
<img width="612" alt="image" src="https://github.com/user-attachments/assets/18317d8a-d6e1-4d16-bbec-2373cff1fbf8" />

# Selective Alignment Transfer for Domain Adaptation in Skin Lesion Analysis

This paper, accepted at the MICCAI 2025 conference, introduces a new method called Selective Alignment Transfer for Domain Adaptation (SAT-DA), a supervised method for skin lesion analysis. The main goal is to improve how deep learning models handle the domain shift between dermoscopic images (taken under controlled conditions) and clinical images (which are more varied in lighting, angles, and quality).

The key mechanism in SAT-DA is its dynamic feature selection. It calculates how important each feature is by comparing the average features from both domains and uses a small neural network to assign a weight to each feature channel. Features that are common and helpful in both domains are kept, while domain-specific noise is reduced. These weighted features are then used for classification.

SAT-DA also introduces two new loss components alongside the standard classification loss:

- Alignment loss to bring the average features of both domains closer together.

- Diversity loss to make sure the model uses a wide range of features instead of relying on just a few.

These changes help the model focus on domain-invariant, diagnostic information while avoiding overfitting to noisy or irrelevant patterns. Compared to existing supervised and unsupervised domain adaptation methods, SAT-DA shows much better performance across several datasets. It also generalises well to unseen data, making it more reliable for real-world clinical settings.

# Dataset 
- ISIC 2017

- ISIC 2018

- Derm7pt-Derm

- Derm7pt-Clinic

- Fitzpatrick17k

- PAD-UFES-20
 
# Evaluation Settings:
Evaluated on three main domain shifts (D7D→D7C, ISIC2017→Fitz, ISIC2018→PAD).

Also tested on four unseen datasets for each setting to measure generalisation.

Compared with both Supervised DA methods (ATDOC, MCC, LIC) and Unsupervised DA methods (DANN, ADDA, Deep CORAL).

Ablation studies were conducted to evaluate the individual contribution of:

- Feature selection

- Alignment loss

- Diversity loss

