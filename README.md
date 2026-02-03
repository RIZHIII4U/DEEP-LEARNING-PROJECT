# DEEP-LEARNING-PROJECT TASK-2

*COMPANY*: CODTECH IT SOLUTIONS

*NAME*: RISHAB GANESH N

*INTERN ID*:  CTIS4236

*DOMAIN*: Data Science

*DURATION*: 4 Weeks

*MENTOR*: NEELA SANTOSH

*DESCRIPTION*: Task-2: 

Synthetic Multivariate Time-Series Generation and Evaluation using TimeGAN

1. Project Description

This project focuses on the generation of high-quality synthetic multivariate time-series data using Time-series Generative Adversarial Networks (TimeGAN) and the systematic evaluation of the generated data through downstream forecasting tasks. The primary objective is to assess whether synthetic time-series data can effectively substitute or augment real-world financial data in predictive modeling scenarios.

The project is structured into two main stages: (i) synthetic data generation using a deep generative model and (ii) quantitative evaluation using supervised machine learning models.

2. Synthetic Data Generation using TimeGAN

The first phase implements TimeGAN, a hybrid generative framework that integrates adversarial learning with supervised sequence modeling. Unlike conventional GANs, TimeGAN preserves temporal dynamics by combining an embedding network, recovery network, generator, supervisor, and discriminator.

The model is trained on real multivariate stock price time-series data stored in an HDF5 format (assets.h5). During training, the embedding and recovery networks learn a latent representation of the temporal structure, while the generator and supervisor jointly ensure that the synthetic sequences follow realistic time-dependent patterns. The discriminator enforces distributional similarity between real and generated sequences.

After training, the model generates synthetic time-series samples that retain the statistical properties and temporal correlations of the original financial data. These synthetic outputs are saved in multiple formats (.npy, .h5, and .xls) to facilitate analysis and reuse.

The implementation is developed using TensorFlow, enabling efficient training and model serialization.

3. Downstream Evaluation using Random Forest

To evaluate the realism and utility of the synthetic data, a downstream forecasting task is conducted using a Random Forest regression model. This evaluation compares predictive performance across three training scenarios:

Models trained solely on real data

Models trained solely on synthetic data

Models trained on a hybrid dataset combining real and synthetic samples

The forecasting models are evaluated using standard regression metrics, including Mean Absolute Error (MAE), Root Mean Square Error (RMSE), and R² score. Comparable performance across these datasets indicates that the synthetic data effectively captures meaningful temporal patterns.

Additionally, Principal Component Analysis (PCA) visualizations and feature importance plots are used to assess distributional alignment and feature-level consistency between real and synthetic datasets. All evaluation pipelines are implemented using scikit-learn.

4. Outputs and Artifacts

Key outputs of the project include:

A trained TimeGAN model checkpoint (TimeSeriesGAN.h5)

Generated synthetic time-series data (synthetic_timeseries.xls)

Evaluation plots embedded within the notebooks (error metrics, PCA plots, feature importance graphs)

5. Notes and Reproducibility

The project is designed to be reproducible on CPU-based systems, with an average training time of 5–10 minutes. While the provided dataset is preprocessed, users may regenerate financial data using yfinance. The synthetic data is not a direct replica but a statistically faithful approximation of the original dataset.

6. References

TimeGAN: Time-series Generative Adversarial Networks (NeurIPS 2019)

TensorFlow

scikit-learn

yfinance
