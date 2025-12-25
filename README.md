## Project Overview

This project focuses on building a **deep learning–based time series forecasting model** to predict the **monthly mean total sunspot number for the next month**. The dataset used (`Sunspot.csv`) contains historical monthly sunspot observations **spanning over 3,200 months, from 1749 to 2018**, where each record represents a date and its corresponding mean total sunspot number. The objective is to learn long-term temporal patterns in solar activity and generate accurate short-term forecasts.

### Dataset and Data Splitting
- The dataset contains just over **3,200 monthly observations**.
- The **first 3,000 samples** were used for training.
- The remaining **~200 samples** were reserved for validation.

### Feature Engineering
- Feature–label pairs were generated using **TensorFlow’s windowing approach**.
- A **window size of 30** was applied:
  - **30 previous months** of sunspot numbers were used as input features.
  - **1 target value** (current month’s sunspot number) was used as the label.
- This setup enables the model to learn temporal dependencies in solar activity.

### Model Architecture
The forecasting model uses a hybrid neural network architecture:
- **1 × 1D Convolutional layer** for local temporal pattern extraction
- **2 × Bidirectional LSTM layers** to capture long-range dependencies
- **3 × Dense layers** for nonlinear transformation
- **1 × Lambda layer** to scale the final output

### Model Performance
- The trained model achieved a **Mean Absolute Error (MAE) of 14.7** on the validation dataset.
- This result indicates effective learning of historical sunspot dynamics and reliable next-month forecasting performance.
