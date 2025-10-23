# AI-ML Assignment 10: Model Explainability

**Name:** Denniz Garza  
**XAI Tool:** SHAP (DeepExplainer)  
**Underlying Model:** Convolutional Neural Network (CNN) trained on MNIST handwritten digits  

---

## Top 3 Global Features
For image models, “features” correspond to pixel regions rather than named variables.  
Based on the **Global SHAP Summary Plot**, the most influential features were:

1. Central pixel clusters forming the **main digit strokes**  
2. Edge pixels that **differentiate rounded digits** (e.g., 0 vs 6, 3 vs 8)  
3. Diagonal stroke intersections that **separate mirrored digits** (e.g., 2 vs 5)

These areas contributed the most to the model’s confidence across all classes.

---

## Analysis Summary

### Case B: Misclassified Instance
The **misclassified instance (Case B)** showed how the model’s focus on misleading pixel regions led to an incorrect prediction.  
According to the SHAP local explanation:

- The model **highlighted irrelevant peripheral pixels** rather than the core stroke pattern.  
- Some positive SHAP values appeared in **blank background regions**, suggesting noise influence.  
- Key stroke areas that normally define the correct digit had **weak SHAP activation**, meaning the CNN underweighted the true distinguishing pattern.  

Overall, the model’s misclassification was driven by **feature attributions concentrated on non-critical pixel regions**, indicating sensitivity to background noise or shape overlap between visually similar digits.

---

## Files in this Repository
- `Explainability.ipynb` — Full notebook including model training, SHAP initialization, and explanation generation.  
- `global_summary_plot.png` — SHAP global explanation visualizing average pixel influence across the dataset.  
- `local_explanation_caseA.png` — Local SHAP explanation for a correctly classified digit.  
- `local_explanation_caseB.png` — Local SHAP explanation for a misclassified digit.  

---

## Youtube Link
https://youtu.be/tf3FT6fC1uM

---

## Description
This project demonstrates **Explainable AI (XAI)** applied to a CNN trained on MNIST.  
It uses **SHAP DeepExplainer** to visualize the contribution of pixel regions to model predictions.  
Through both **global** and **local** explanations, it reveals which image areas most strongly influence correct and incorrect predictions — providing transparency into the model’s reasoning and error patterns.

