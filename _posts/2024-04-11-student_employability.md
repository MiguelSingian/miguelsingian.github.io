---
layout: single
title:  "From Class to Career"
date: 2024-04-11 15:35:00 +0800
categories: "works"
tags: "explainability machine_learning classifier xgboost dice shapley"
header:
    overlay_image: "assets/images/Screenshot 2024-05-27 at 8.24.07 PM.png"
---

Predicting Student Employability and Personalizing Advice Through Machine Learning Using Mock Interview Results

![Group Pic](/assets/images/viber_image_2024-05-27_20-06-14-111.jpg)

This paper was presented at the 2024 Asian Institute of Management Machine Learning 2 public presentation event, together with my classmates and colleagues, Ian CoKehyeng, Rex Laylo, Gregory Uy, and John Cris Orenday.

![Dataset](/assets/images/Screenshot 2024-05-27 at 8.07.18 PM.png)

Using *Random Undersampling* and an *XGBoost Classifier* model, we showed that it possible to predict the employability assessment given to Technological Instutute of the Philippines students by their OJTs using only mock-interview results at an 85% accuracy.

![DICE](/assets/images/Screenshot 2024-05-27 at 8.09.25 PM.png)

Furthermore, we demonstrated using *DICE Counterfactual Explanations* how a students' employability score may be improved through the smallest change in soft skills as assessed by the mock interviews. For example, if this student increases their "general appearance" score, they're much more likely to be assessed as emplyable.

![Deployment](/assets/images/Screenshot 2024-05-27 at 8.10.06 PM.png)

Finally, we found that as few as 500 mock interview results, a feasible number for a university to collect, already achieves an 80% accuracy. 

The full notebook can be accessed [here](https://github.com/MiguelSingian/school-projects/blob/main/employability.ipynb), and the paper can be accessed [here](https://github.com/MiguelSingian/school-projects/blob/main/employability_paper.pdf).