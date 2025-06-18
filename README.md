# Dynamic Queue Allocation using AI

This project leverages AI to optimize queue management by predicting queue lengths and counter allocations based on historical and real-time data. The solution uses **XGBoost** for multi-output regression to make accurate predictions and improve customer experience in service environments.

## Table of Contents

* [Overview](#overview)
* [Dataset](#dataset)
* [Preprocessing](#preprocessing)
* [Model Training](#model-training)
* [Results](#results)
* [Installation](#installation)
* [Usage](#usage)
* [Features](#features)
* [Visualizations](#visualizations)
* [Model Saving & Loading](#Model-Saving-&-Loading)


---

## Overview

This project focuses on dynamic queue management by predicting:

* Queue Length: Number of customers waiting in line.
* Counter Number: Optimal counter allocation to reduce wait times.

The model analyzes data such as:

* Arrival, start, and finish times
* Customer demographics (age, gender, payment method)
* Service time variations (peak/off-peak hours)

---

## Dataset

### Features

The dataset includes:

* **Queue-Length**: Historical queue data.
* **Counter-Number**: Number of active counters.
* **Customer Demographics**: Age, gender, payment method.
* **Time-Based Attributes**: Arrival, start, finish, and wait times.
* **Temporal Factors**: Day of the week.

### Source

The dataset is collected from a simulated or real-world service environment to capture both peak and off-peak behaviors.

---

## Preprocessing

Key preprocessing steps:

1. **Missing Values**: Numeric features filled with mean values; categorical features filled with mode.
2. **Time Conversion**: Time columns converted to seconds for standardization.
3. **One-Hot Encoding**: Encoded categorical variables like `gender` and `payment_method`.
4. **Feature Scaling**: Ensured compatibility for training.

---

## Model Training

### Algorithm

* **XGBoost**: Chosen for its efficiency and ability to handle structured data.
* **MultiOutputRegressor**: Used to predict multiple targets (Queue Length & Counter Number).

### Hyperparameters

* `n_estimators`: 100
* `learning_rate`: 0.1
* `max_depth`: 6
* `random_state`: 42

---

## Results

### Performance Metrics

* **RMSE (Root Mean Square Error)**:

  * Queue Length: *calculated value*
  * Counter Number: *calculated value*
* **Accuracy**:

  * Queue Length: *accuracy percentage*
  * Counter Number: *accuracy percentage*

### Visualizations

* Actual vs. Predicted Values
* Feature Importance Plots
* Correlation Heatmaps

---

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/defected-rbc/dynamic-queue-allocation.git
   cd dynamic-queue-allocation
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Ensure you have a suitable dataset in Excel format ready for upload.

---

## Usage

1. Open the notebook or script in Google Colab or your local environment.
2. Upload the dataset when prompted.
3. Execute all cells to train the model, view results, and save the trained model.

---

## Features

* **AI-Driven Queue Management**: Optimize counter allocation and minimize customer wait times.
* **Multi-Target Prediction**: Simultaneous prediction of queue length and counter allocation.
* **Visualization**: Gain insights using feature importance plots and correlation heatmaps.
* **Model Persistence**: Save and load trained models with Joblib.

---

## Visualizations

### Feature Importance

* Analyze which features have the most significant impact on predictions.

### Heatmaps

* Visualize correlations among dataset features.

### Scatter Plots

* Compare actual vs. predicted values for both targets.

---

## Model Saving & Loading

* **Save Model**: Automatically saves the trained XGBoost model as a `.joblib` file in Google Drive.
* **Load Model**: Reload the trained model to make new predictions.

