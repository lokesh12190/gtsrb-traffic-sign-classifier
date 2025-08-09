# Traffic Sign Recognition for ADAS using EfficientNetB0 & Weights & Biases

## Overview

In modern road safety systems, the ability for a machine to quickly and accurately recognize traffic signs is more than a convenience — it’s a necessity.  
Whether it’s **Advanced Driver Assistance Systems (ADAS)** or fully **autonomous vehicles**, traffic sign recognition allows vehicles to obey speed limits, follow road directions, and react to warnings in real time.  

This project tackles exactly that challenge using the **German Traffic Sign Recognition Benchmark (GTSRB)** — a well-known dataset containing 43 different types of traffic signs, collected from real-world driving conditions.  
The signs vary in **size, lighting, rotation, and occlusion**, making the dataset a realistic and challenging benchmark.

---

## Why This Data is Critical

Traffic signs in the real world are not captured under perfect conditions. A speed limit sign might be half-hidden by a tree, a warning sign could be slightly tilted, or the image could be taken in low light or under bright glare.  

The GTSRB dataset captures these **real-life imperfections**:
- Varying brightness and contrast
- Partial occlusion
- Rotations and perspective distortion
- Different distances from the camera

Training a model on this kind of data means it will **generalize well** to real driving situations, making it directly applicable to **ADAS** and self-driving systems.

---

## What I Did

I started by preparing the dataset — resizing all images to match **EfficientNetB0**’s expected input size and normalizing pixel values.  
To make the model robust, I applied **data augmentation**: rotations, zooms, translations, and scaling.  

For the model, I chose **EfficientNetB0** — a network known for achieving high accuracy with relatively few parameters. I used ImageNet pretrained weights, replaced the top classification layer with one suitable for 43 classes, and fine-tuned the model on the GTSRB dataset.

To ensure every experiment was tracked and reproducible, I integrated **Weights & Biases (wandb)**. This let me:
- Log metrics like accuracy, loss, precision, recall, and F1 score in real-time
- Visualize training and validation curves
- Save model checkpoints
- Compare different hyperparameter runs

I also performed **parameter tuning** — adjusting batch size, learning rate, augmentation settings, and number of epochs to squeeze out every bit of accuracy without overfitting.

---

## What I Achieved

After training and tuning, the model reached:
- **Accuracy:** 99.74%
- **Precision:** 99.74%
- **Recall:** 99.74%
- **F1 Score:** 99.74%

It can reliably distinguish between all 43 traffic sign categories, even in challenging scenarios.

---

## Repository Guide

- **`data/`** – Information about the dataset, its types, and how to access it. *(Dataset files are not stored in the repo due to size.)*  
- **`logs/`** – Plots, confusion matrices, and visual results from training and evaluation.  
- **`main/`** – Main Jupyter Notebook containing all preprocessing, training, evaluation, and logging code.  
- **`requirements.txt`** – Python dependencies for running the project.  
- **`README.md`** – This file, describing the project.

---

## Dataset Citation

The dataset is free to use, but the authors request that you cite:

> J. Stallkamp, M. Schlipsing, J. Salmen, and C. Igel. *The German Traffic Sign Recognition Benchmark: A multi-class classification competition.* In Proceedings of the IEEE International Joint Conference on Neural Networks, pages 1453–1460. 2011.


