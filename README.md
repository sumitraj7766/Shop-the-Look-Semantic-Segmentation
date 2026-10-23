# 🛍️ Shop the Look — Semantic Segmentation for Fashion

**A Deep Learning project for pixel-level clothing segmentation using PyTorch and U-Net.**

Shop the Look explores how computer vision can identify clothing regions in fashion images. The project implements semantic segmentation to classify image pixels into clothing and accessory categories, supporting potential applications in fashion search, visual product discovery, and automated image understanding.

## 📌 Project Overview

Fashion images often contain multiple garments, accessories, skin, hair, and background elements. Semantic segmentation assigns a class label to each pixel, allowing the model to distinguish these regions.

This project compares two deep learning architectures:

- **Encoder–Decoder CNN:** A baseline segmentation model.
- **U-Net:** An encoder–decoder architecture with skip connections to preserve spatial information and improve segmentation quality.

Both models are trained and evaluated using the Clothing Co-Parsing dataset.

## ✨ Key Features

- Pixel-level semantic segmentation of fashion images.
- PyTorch implementation of a U-Net architecture.
- Baseline encoder–decoder versus U-Net comparison.
- Seven semantic segmentation classes.
- Weighted cross-entropy loss to address class imbalance.
- Mean Intersection over Union (mIoU) evaluation.
- Data augmentation using horizontal flips and brightness adjustments.
- Cosine learning-rate scheduling.
- Model checkpoint saving and reload verification.

## 🧠 Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming language |
| PyTorch | Deep learning framework |
| NumPy | Array and dataset processing |
| Matplotlib | Visualization and evaluation plots |
| Google Colab | Cloud-based experimentation |
| U-Net | Semantic segmentation architecture |

## 👕 Segmentation Classes

The model predicts one of seven classes for each pixel:

1. Background
2. Skin & hair
3. Top
4. Bottom
5. Dress
6. Footwear
7. Bag & accessories

## 📊 Dataset

**Dataset:** [Clothing Co-Parsing](https://github.com/bearpaw/clothing-co-parsing)

The notebook uses a dataset archive named `fashion_parsing.npz`, containing 1,004 street-fashion images.

### Dataset split

| Split | Number of images |
|---|---:|
| Training | 800 |
| Validation | 100 |
| Testing | 104 |
| **Total** | **1,004** |

The images are resized to **96 × 128 pixels (width × height)** for model training and evaluation.

*Dataset redistribution and licensing conditions should be checked against the original source before redistributing the dataset archive.*

## 🏗️ Model Architecture

### 1. Encoder–Decoder CNN

The baseline model encodes input images into feature representations and progressively upsamples them to generate pixel-level predictions.

### 2. U-Net with Skip Connections

U-Net connects corresponding encoder and decoder stages through skip connections. These connections help preserve spatial details that can be lost during downsampling.

The network produces a seven-class segmentation map for each input image.

## 📈 Results

The following results were recorded in the Google Colab notebook.

| Model | Evaluation | Mean IoU |
|---|---|---:|
| Encoder–Decoder CNN | Validation | 0.477 |
| U-Net | Validation | 0.517 |
| U-Net | Test | **0.547** |

The U-Net achieved a test mean IoU of **54.7%**. Its saved checkpoint was reloaded and evaluated again, reproducing the reported test score.

**Metric:** Mean Intersection over Union (mIoU), which measures the overlap between predicted and ground-truth regions across segmentation classes.

*Note: The baseline model's numerical test mIoU is not included here because a confirmed value was not available in the recorded notebook output.*

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/sumitraj7766/Shop-the-Look-Semantic-Segmentation.git
cd Shop-the-Look-Semantic-Segmentation
```

Install the required libraries:

```bash
pip install torch numpy matplotlib
```

For the original notebook workflow, Google Colab is recommended. The dataset archive and trained model must be available at the paths expected by the notebook.

## 🚀 How to Run

1. Open `Shop_the_Look.ipynb` in Google Colab.
2. Download the dataset from its original source, subject to its applicable terms.
3. Upload or mount the dataset in the runtime.
4. Execute the notebook cells in order to preprocess the data, train the models, and evaluate segmentation performance.
5. Inspect the validation and test results.
6. Load `models/fashion_unet.pt` if the trained checkpoint is included and you want to evaluate the saved model rather than retrain it.

**Important:** The notebook and trained checkpoint are separate files. Running the notebook from scratch requires the dataset and a compatible runtime environment.

## 📁 Suggested Repository Structure

```text
Shop-the-Look-Semantic-Segmentation/
├── README.md
├── Shop_the_Look.ipynb
├── requirements.txt
└── models/
    └── fashion_unet.pt
```

The dataset archive is intentionally omitted from this suggested structure until its redistribution terms have been verified.

## 🔮 Future Improvements

- Train at higher image resolutions.
- Improve segmentation of small accessories and footwear.
- Explore pretrained encoders and transfer learning.
- Compare U-Net with DeepLabV3+ and other segmentation architectures.
- Report per-class IoU and pixel accuracy.
- Add visual comparisons of input images, ground-truth masks, and predictions.
- Develop a simple interface for uploading fashion images and viewing segmentation results.

## 🎯 Applications

Potential applications include:

- Fashion image understanding.
- Clothing-region extraction.
- Visual fashion search.
- Fashion marketplace image processing.
- Garment-focused image analysis.

These are potential applications of the approach, not claims of a deployed product.

## 👨‍💻 Author

**Sumit Kumar**

- GitHub: [@sumitraj7766](https://github.com/sumitraj7766)

## 🙌 Acknowledgements

Thanks to the authors of the [Clothing Co-Parsing dataset](https://github.com/bearpaw/clothing-co-parsing) for providing a dataset for research in clothing parsing and fashion image understanding.

---

If you find this project useful, consider giving the repository a ⭐ on GitHub.
