---
layout: single
title:  "How Competitive is my Powerlifting Total? Part 2: Machine Learning"
date: 2023-12-10 15:35:00 +0800
categories: "works"
tags: "machine_learning time_series feature_engineering"
header:
    image: "assets/images/powerlifting/Screenshot1.png"
---

Time Series \| XGBoost \| Machine Learning \| Feature Engineering

Being an insecure athlete, I was not satisfied with merely knowing how my current total would stack up in competition--I wanted to know potentially what my *future* powerlifting total would be. 

To do this, rather than train my own body, I trained a machine learning model to take a athlete's measurements, current squat, bench press, and deadlift numbers, and target competition date, and return the predicted numbers for that competition (given consistent training at the level of an average IPF athlete).

This is part two of a two-part series. [Read part one here.](https://miguelsingian.github.io/works/2023/02/03/powerlifting_1.html)

The biggest challenge of this project was the *time series* element of it. If the model must use past performance to inform future performance, then it must be trained on past performance informing future performance. To do this, I combined every athlete's result with other results of the same athlete, such that the model now sees a "past performance", a "future performance" and a "time delta" per row.

![Screenshot of Taylor Atwood's competition results, with arrows showing that each result is paired with another](/assets/images/powerlifting/Screenshot2.png)
*Screenshot of Taylor Atwood's competition results, with arrows showing that each result is paired with another.*

This was inspired by the methodology of [Medina-Romero and colleagues (2023)](https://www.mdpi.com/2673-4591/39/1/20). 

Additionally, since this was a *multioutput regression* task where three numbers are being predicted (squat, bench press, deadlift), I trained three ML models. If I were to do this again in the future, I would choose a model that is better suited to multioutput regression.

After that, it was a simple matter of doing a grid search over popular machine learning algorithms. The best model with XGBOOST. Here are the results for the three lifts:

![Results](/assets/images/powerlifting/Screenshot 2024-05-14 at 10.21.53 PM.png)

Notably, the model performed better on *male* athletes, with a mean absolute error of 10.9kg vs 15.8kg for female athletes. This could be because of a gender imbalance in the training data, or even a greater variance in female performance vs male.

![Gender Results](/assets/images/powerlifting/Screenshot 2024-05-14 at 10.24.33 PM.png)

It also interestingly had varying performance between age groups, with the performance breaking down at older age groups.

![Age Results](/assets/images/powerlifting/Screenshot 2024-05-14 at 10.27.55 PM.png)

You will find the full notebook, including the full exploratory data analysis, [here](https://github.com/MiguelSingian/school-projects/blob/main/powerlifting.ipynb).