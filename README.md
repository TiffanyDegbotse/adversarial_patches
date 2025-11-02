# Adversarial Patches – ImageNet (Explainable AI Demo)

This project explores **adversarial patch attacks** — small, printable image regions that can fool deep learning models such as ResNet-34 into misclassifying objects. The work is based on **Phillip Lippe’s original tutorial**, with modifications by **Dr. Brinnae Bent** for the course *Emerging Trends in Explainable AI* at Duke University.

---

## Overview

Adversarial patches show how neural networks can be deceived by adding localized visual perturbations that dominate the model’s attention.  
This notebook trains, evaluates, and visualizes adversarial patches for several ImageNet classes, demonstrating how these attacks generalize across different inputs.

---

## Key Features

- **Pretrained Model Setup:** Loads a ResNet-34 model pretrained on ImageNet and freezes its weights for inference.  
- **Data Preparation:** Normalizes TinyImageNet samples using ImageNet mean and standard deviation values.  
- **Patch Training:** Optimizes a learnable patch tensor to mislead the model into predicting a specific target class.  
- **Evaluation:** Computes Top-1 and Top-5 success rates of the adversarial patch.  
- **Visualization:** Displays original vs. adversarial predictions, patch grids, and noise patterns.  
- **Export Tools:** Saves trained patches as high-resolution printable PNGs and combines them into a single sequence for physical experiments.  
- **Decoding Demo:** Uses the pretrained model to classify photographed patches and decode hidden messages (e.g., “XAI”).

---

## Main Functions

| Function | Description |
|-----------|-------------|
| **eval_model()** | Evaluates model Top-1 and Top-5 accuracy. |
| **show_prediction()** | Displays an image, its top-K predictions, and optionally adversarial noise. |
| **patch_attack()** | Trains an adversarial patch targeting a specific ImageNet class. |
| **eval_patch()** | Computes targeted attack success rates. |
| **get_patches()** | Loads or trains multiple patches across chosen classes and sizes. |
| **show_patches()** | Displays a grid of trained patches by class and patch size. |
| **save_patch_png()** | Saves patches as printable PNG files. |
| **make_sequence_image()** | Combines multiple patch PNGs into a single horizontal composite. |
| **decode_sequence_from_photo()** | Decodes a photographed patch sequence into predicted message letters. |

---

## Classes and Patch Sizes

Trained target classes include:

`['toaster', 'goldfish', 'school bus', 'lipstick', 'pineapple', 'tennis ball']`

Patch sizes used: **32×32**, **48×48**, and **64×64**

---

## Example Workflow

1. **Train or Load Patches**  
   Generate or retrieve pretrained adversarial patches for multiple classes and patch sizes, then save their results.

2. **Visualize Patches**  
   Display the trained patches arranged by size and target class.

3. **Save Printable Patch Images**  
   Convert the trained patch tensors into high-resolution printable PNGs.

4. **Combine Patches into a Sequence**  
   Merge multiple patch images side-by-side into one horizontal composite for testing or visualization.

5. **Decode Photographed Sequence**  
   Upload a photo of the printed sequence and classify each segment to reconstruct the encoded message.

---

## Dependencies

- Python 3.9 or higher  
- PyTorch  
- Torchvision  
- NumPy  
- Matplotlib  
- Pillow  
- tqdm  
- tabulate  
- IPython

Install dependencies with:

`pip install torch torchvision numpy matplotlib pillow tqdm tabulate`

---

## Educational Context

This project is intended for **educational and research use** in explainable AI, adversarial robustness, and trustworthy AI systems.  
It provides a hands-on illustration of how small visual perturbations can mislead powerful neural networks — highlighting the need for transparency, interpretability, and robust model evaluation.

---

## Credits

- Original tutorial by **Phillip Lippe**  
- Modified for Duke University by **Dr. Brinnae Bent**  
- Course: *Emerging Trends in Explainable AI*  
- Further extensions and experimentation by **Tiffany Degbotse (2025)**

---
