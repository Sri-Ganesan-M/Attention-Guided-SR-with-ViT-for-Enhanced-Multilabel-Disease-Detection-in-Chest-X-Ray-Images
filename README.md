# README: Attention-Guided Super Resolution in Visual Transformers for Enhanced Multilabel Disease Detection in Chest X-ray Images

## 📌 Overview

This repository contains the implementation of a deep learning pipeline that combines **Vision Transformers (ViT)** and **Latent Diffusion Models (LDM)** for enhanced multilabel disease detection in chest X-ray images. The approach leverages attention maps to identify diagnostically significant regions, applies super-resolution to enhance these regions, and achieves state-of-the-art classification performance.

---

## 🚀 Key Features

- **Vision Transformers (ViT)**: Captures global dependencies in medical images for accurate multilabel classification.

- **Attention Maps**: Highlights regions of clinical interest, improving interpretability for clinicians.

- **Latent Diffusion Models (LDM)**: Enhances image resolution in high-attention regions, improving diagnostic clarity.

- **High Performance**: Achieves **98.23% validation accuracy** on chest X-ray datasets.

---

## 📊 Results

### Performance Metrics

| Model                     | Validation Accuracy | Validation Loss |

|---------------------------|---------------------|-----------------|

| Base ViT Model            | 96.01%              | 0.34            |

| ViT + Super-Resolution    | **98.23%**          | **0.31**        |

### Super-Resolution Metrics

| Image Type          | PSNR   | SSIM    |

|---------------------|--------|---------|

| Original Image      | Inf    | 1.0000  |

| Super-Resolved Image| 46.58  | 0.9879  |

---

## 🛠️ Methodology

1\. **Data Preprocessing**:

   - Resize images to 224x224 pixels.

   - Normalize and augment data (rotation, flipping, affine transformations).

2\. **Vision Transformer (ViT) Training**:

   - Fine-tune a pre-trained ViT model (`google/vit-base-patch16-224-in21k`) for multilabel classification.

   - Extract attention maps to identify high-importance regions.

3\. **Super-Resolution with LDM**:

   - Apply the pre-trained LDM model (`CompVis/ldm-super-resolution-4x-openimages`) to enhance high-attention regions.

   - Reintegrate enhanced regions into the original images.

4\. **Re-training and Evaluation**:

   - Retrain ViT on the enhanced dataset.

   - Evaluate performance using accuracy, PSNR, and SSIM metrics.

---

## 📂 Dataset

- **Source**: Chest X-ray images labeled for multiple conditions (e.g., Cardiomegaly, Pneumonia, Atelectasis).

- **Class Distribution**:

  | Condition               | Percentage |

  |-------------------------|------------|

  | Enlarged Cardiomediastinum | 3.89%      |

  | Cardiomegaly            | 7.28%      |

  | Lung Opacity            | 16.32%     |

  | Pleural Effusion        | 15.54%     |

  | **Total Samples**       | **77,857** |

---

## 🖼️ Visualizations

- **Attention Maps**: Highlight diagnostically relevant regions (e.g., lungs for Pneumonia).

- **Super-Resolution**: Enhances clarity of critical areas (e.g., pleural effusion).

![Attention Map Visualization](figures/attention_map.png)  

*Example of attention map overlay on a chest X-ray.*

---

## 🔧 Installation

1\. Clone the repository:

   ```bash

   git clone https://github.com/your-repo/medical-vit-super-resolution.git

   cd medical-vit-super-resolution

   ```

2\. Install dependencies:

   ```bash

   pip install -r requirements.txt

   ```

3\. Download pre-trained models:

   - ViT: `google/vit-base-patch16-224-in21k`

   - LDM: `CompVis/ldm-super-resolution-4x-openimages`


---

## 📚 References

1\. Mehri, A., et al. (2024). *TnTViT-G: Dual-stream transformer-based super-resolution for visible-guided infrared image enhancement.* IEEE Transactions on Image Processing.  

2\. Oommen, L., et al. (2024). *Conv-attention vision transformer (CA-ViT) for multi-label chest X-ray classification.* Pattern Recognition Letters.  

3\. Rombach, R., et al. (2022). *High-resolution image synthesis with latent diffusion models.* CVPR.

---

## ✨ Future Work

- Extend the model to 3D imaging (CT/MRI).

- Integrate super-resolution for other medical imaging modalities.

---

For questions or collaborations, please contact **Lekshmi Kalinathan** at [lekshmi.k@vitstudent.ac.in](mailto:lekshmi.k@vitstudent.ac.in).  

⭐ **Star this repo if you find it useful!** ⭐
