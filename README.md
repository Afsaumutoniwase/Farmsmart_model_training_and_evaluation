# 🌿 FarmSmart: Model Training and Evaluation

**Author:** Afsa Umutoniwase  
**Program:** BSc in Software Engineering, African Leadership University

---

## Project History

**FarmSmart: ML-Driven Hydroponic Farming for Climate-Resilient Agriculture in Rwanda**

Agricultural productivity in Rwanda is constrained by unpredictable weather, declining soil fertility, and inefficient use of water and nutrients. **FarmSmart** proposes the integration of **hydroponic farming systems** with **machine learning (ML)** to increase yields, optimize resource usage, and promote sustainable practices.

Our system leverages sensor data and predictive algorithms to recommend real-time optimal growing conditions. Theoretical modeling shows potential for a **20–30% yield increase** and **40% reduction in water use** over traditional methods.

The project is targeting smallholder farmers in peri-urban areas and seeks future pilot partnerships with **Green City Kigali** and **RYAF**.

---

## Introduction and Motivation

Agriculture employs over **70% of Rwanda's population**, yet faces increasing threats from land degradation, climate change, and inefficient traditional practices. There is an urgent need for **scalable, tech-driven agricultural solutions**.

Hydroponics offers a **soil-free, water-efficient** alternative to traditional farming. FarmSmart leverages **AI and localized environmental data** to help farmers make intelligent, data-driven decisions that lead to:

- Higher crop yields  
- Reduced resource consumption  
- Greater climate resilience  
- Youth engagement in agri-tech  

---

## Problem Statement

While **AI-powered hydroponics** have shown impressive global results—with **up to 10x yield improvements** in studies like Shreenidhi et al. (2021) and FAO trials (2025)—they remain **inaccessible to smallholder farmers** due to high costs and technical complexity.

Most systems (e.g., **AgriLyst, CropX**) target large-scale operations, leaving behind farmers in Rwanda, where hydroponics remains **manual, expensive, and hard to scale**.

**FarmSmart** addresses this gap with an **AI-enhanced hydroponic platform**, tailored to Rwanda’s context. By integrating **affordable IoT sensors** with ML models, FarmSmart enables **real-time, precision farming** for smallholders—improving yields, resource use, and climate resilience.

---

## Dataset Summary

**Download:** [HydroFarm Dataset (figshare)](https://figshare.com/articles/dataset/Dataset_HydroFarm/28340516/1?file=52114643)

- **Classes:** `healthy`, `unhealthy`
- **Structure:** Split into `train`, `test`, and `validation` directories, each with subfolders per class.
- **Format:** JPEG/PNG images, resized to **240x240** pixels
- **Usage:** Designed for deep learning using **TensorFlow/Keras**, and supports VGG16-based feature extraction.
- **Tools:** ImageDataGenerator for preprocessing; Google Colab or Jupyter Notebook recommended.

---

## Model Training Overview
| Instance | Model                        | Optimizer | Regularization | Epochs | Early Stopping | Layers                 | Learning Rate | Accuracy | F1 Score | Recall | Precision | Loss    |
|----------|------------------------------|-----------|----------------|--------|----------------|------------------------|----------------|----------|----------|--------|-----------|---------|
| 1        | CNN                          | Adam      | None           | 20     | Yes            | 8                      | 0.0005         | 0.6883   | 0.7000   |  0.7179 | 0.6829  | 0.6417 |
| 2        | CNN                          | Adam      | L1             | 15     | Yes            | 8                      | 0.0001         | 0.4935   | 0.6609   | 0.9744 | 0.5000   | 5.2036 |
| 3        | CNN                          | RMSprop   | L2             | 20     | Yes            | 8                      | 0.0005         | 0.5584   | 0.2917   | 0.1795 | 0.7778   | 0.7839 |
| 4        | CNN                          | RMSprop   | L1             | 15     | Yes            | 8                      | 0.0001         | 0.5455   | 0.6847   |0.9744  | 0.5278   | 5.0626|
| 5        | VGG16 + Logistic Regression  | N/A       | None           | N/A    | No             | 1 (Logistic Regression) | N/A            | **0.9610** | **0.9620** | **0.9700** | **0.9500** | N/A     |

**Best model:** Instance 5 (VGG16 + Logistic Regression)
---

## Model Evaluation Strategy

- All models evaluated on the **same test set**
- Metrics used:
  - **Accuracy**
  - **F1 Score**
  - **Precision**
  - **Recall**
- **Best-performing model** is saved to `saved_models/best_model.h5` or `.pkl`
- Fallback logic ensures predictions work regardless of model type

# Video
**Watch:** [Presentation Video](https://figshare.com/articles/dataset/Dataset_HydroFarm/28340516/1?file=52114643)

---
