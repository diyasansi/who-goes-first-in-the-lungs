# 🩺 Who Goes First in the Lungs  
*A decision-support tool for prioritising care, not replacing it*

---

## Why This Project Exists

In high-pressure healthcare settings, clinicians are often forced to make rapid decisions about who needs attention first. When time, staff, and resources are limited, even a short delay can matter.

This project explores how machine learning can support those moments by analyzing chest X-ray images and ranking cases by urgency. Rather than attempting to diagnose patients, the system is designed to surface images that may warrant earlier review, helping clinicians prioritize their attention when workloads are high.

The emphasis throughout this work is on interpretability, clinically meaningful evaluation, and responsible use of machine learning as a decision-support tool—not a replacement for expert judgment.

---

## What the Model Does (and Does Not Do)

This system analyses chest X-ray images and produces:
- A **predicted class** (NORMAL or PNEUMONIA)
- A **confidence score**, indicating how strongly the model associates the image with pneumonia-related patterns

These outputs can be used to:
- Flag cases that may require **earlier attention**
- Assist clinicians during periods of overload
- Provide an additional signal when triaging large volumes of imaging data

However, it is essential to be clear:

> **This model does not diagnose patients.**  
> It does not replace radiologists, clinicians, or medical judgment.

All predictions should be interpreted **in context**, alongside clinical expertise and patient history.

---

## How the System Works 

- Chest X-ray images are standardised through preprocessing
- Images are converted into numerical representations using **Histogram of Oriented Gradients (HOG)**
- Multiple classical machine learning models are trained and evaluated
- Models are compared using clinically meaningful metrics, with a strong focus on **false negatives**
- The final model is selected to prioritise **minimising missed pneumonia cases**

This approach favours **interpretability, transparency, and reproducibility** over complexity.

---

## Bias, Fairness, and Ethical Considerations

Bias is an unavoidable concern in any machine learning system, particularly in healthcare.

This project attempts to reduce bias by:
- Using chest X-ray images that do **not explicitly encode demographic information** such as gender, ethnicity, or socioeconomic status
- Avoiding the use of patient metadata as model input
- Focusing on **visual lung patterns** rather than personal characteristics

However, important limitations remain:
- The dataset is **imbalanced**, with a higher proportion of pneumonia cases
- The data may reflect historical or systemic biases from its source
- The absence of explicit demographic information does **not guarantee fairness**

As a result:
- The model cannot be assumed to perform equally across all populations
- Ongoing evaluation and validation are essential in any real-world use

---

## Continuous Learning Is Essential

Medical data evolves. Imaging protocols change, patient populations shift, and disease presentation can vary.

For this reason:
- The model should be **continuously retrained and tested** on newer data
- Performance should be monitored for drift and bias
- Decision thresholds may need adjustment based on clinical priorities

---

## Intended Use

✔️ Clinical decision support  
✔️ Triage prioritisation  
✔️ Research and educational purposes  

❌ Automated diagnosis  
❌ Standalone medical decision-making  
❌ Replacement for expert review  

---

## 📁 Data Availability and Privacy

The raw chest X-ray images used in this project are **not included in this repository**.

The dataset this project uses can be found here:  
https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia

Although the dataset is publicly accessible for research and educational purposes on Kaggle, *public availability does not imply permission to redistribute*. Kaggle hosts the data, but the images themselves are subject to licensing and usage restrictions set by their original creators. In many medical datasets, redistribution—especially on public platforms like GitHub—is explicitly discouraged or prohibited.

Medical imaging data also carries important ethical considerations: even when images are anonymised, they originate from real patients. To respect these constraints and avoid unintended misuse, this repository excludes all raw medical images.

Instead, this project focuses on:
- The **methodology** for preprocessing and feature extraction
- The **modelling and evaluation pipeline**
- **Derived outputs** such as plots, metrics, and example visualisations
- Clear instructions for how to download the dataset and reproduce the workflow locally

Users who wish to reproduce the results can download the dataset from the Kaggle link above and follow the provided instructions to generate features and train models.

This approach prioritises **ethical data use, reproducibility, and transparency**, while respecting patient privacy and dataset licensing requirements.


