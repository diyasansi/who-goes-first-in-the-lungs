# 🩺 Chest X-Ray Triage with Machine Learning  
*A decision-support tool for prioritising care, not replacing it*

---

##  Why This Project Exists

In healthcare, especially during periods of extreme pressure—such as pandemics, staff shortages, or high patient volumes—**time becomes one of the most limited resources**. Clinicians are often required to make rapid decisions about which patients to assess first, knowing that delays can have serious consequences.

This project was built with that reality in mind.

Rather than attempting to **diagnose** patients, the goal of this project is to **support clinical triage**:  
to help **rank chest X-ray images by urgency**, allowing medical professionals to prioritise which cases may require earlier review when workloads are high.

At its core, this is a **decision-support system**, not a diagnostic tool.

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

