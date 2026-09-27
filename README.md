# BB84 QKD QBER Prediction & Quantum Machine Learning Platform

An end-to-end Quantum Key Distribution (QKD) platform for simulating BB84 quantum communication, predicting Quantum Bit Error Rate (QBER), and evaluating communication security under different channel conditions.

The platform combines classical Machine Learning and Quantum Machine Learning models to analyze and predict QBER.

## Features

- BB84 Quantum Key Distribution simulation
- Quantum channel modeling
- QBER calculation and prediction
- Channel loss and noise modeling
- Polarization/basis misalignment modeling
- Detector efficiency and dark-count modeling
- Classical Machine Learning models
- Quantum Machine Learning models
- Security assessment using QBER threshold
- Secret Key Rate (SKR) estimation
- Model benchmarking
- Parameter sensitivity analysis
- Batch CSV prediction
- Interactive web dashboard
- REST API support

## Models

The platform evaluates four prediction models:

| Model | Type |
|---|---|
| Random Forest | Classical ML |
| XGBoost | Classical ML |
| VQR | Quantum ML |
| HQNN | Hybrid Quantum ML |

### Benchmark Results

All models are evaluated using the same held-out test dataset.

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Random Forest | 0.0344 | 0.1019 | 0.5189 |
| XGBoost | 0.0353 | 0.1056 | 0.4840 |
| VQR | 0.0398 | 0.1073 | 0.4664 |
| HQNN | 0.0376 | 0.0925 | 0.6037 |

HQNN achieved the highest R² and lowest RMSE among the evaluated models on the held-out simulated benchmark.

## QKD Simulation

The system simulates the BB84 protocol using:

- Alice and Bob
- Random bit generation
- Random basis selection
- Quantum state encoding
- Quantum measurement
- Basis reconciliation
- Channel noise
- Channel loss
- Misalignment
- Detector inefficiency
- Dark counts

The resulting communication data is used to calculate ground-truth QBER.

## Input Parameters

The prediction system uses the following channel parameters:

- Channel Loss
- Noise Probability
- Polarization/Basis Misalignment
- Detector Efficiency
- Dark Count Rate

These parameters are varied to generate different QKD channel conditions.

## Dataset

The benchmark dataset is generated using our own BB84 QKD simulation environment.

Each generated sample contains channel parameters and the corresponding simulated QBER.

The dataset is processed using:

1. Data cleaning
2. Feature preparation
3. Normalization
4. Train-test splitting
5. Model training
6. Model evaluation

The models are evaluated on the same held-out test dataset for fair comparison.

## Security Analysis

The platform uses an asymptotic BB84 QBER reference threshold of 11%.

```text
QBER ≤ 11%  → Secure
QBER > 11%  → Abort
