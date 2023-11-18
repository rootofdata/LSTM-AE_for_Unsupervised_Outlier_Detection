# LSTM-AE_for_Unsupervised_Outlier_Detection
An innovative framework for indoor air quality outlier detection, comprising three modules: LSTM-AE-based reconstruction error detector, latent feature class-assisted SVM detector, and an ensemble model for robust real-time anomaly detection. Ideal for industrial applications, providing stable and versatile outlier decision rules.
  
Remark : [http://doi.or.kr/10.1186/s40537-023-00746-z](http://doi.or.kr/10.1186/s40537-023-00746-z)

## Introduction
This thesis emphasizes the growing importance of detecting indoor air pollution (IAP) due to increased environmental awareness. IAP is considered a higher risk than outdoor air pollution because of prolonged indoor exposure. Continuous exposure to pollutants can lead to serious health risks. Researchers are working on strategies to control indoor air quality, with a focus on major factors like total volatile organic compounds (TVOC) and CO2, as well as outlier detection.

Outlier detection is crucial for identifying abnormal values or patterns in large datasets. The thesis proposes using an artificial intelligence-based outlier detection model to address the challenges of varying environments. It suggests using a long short-term memory autoencoder (LSTM-AE) for multivariate time-series data outlier detection, with the aim of robustly applying it across different indoor environments. and also highlights the need for considering noise in sensor data and using unsupervised detection methods.

The proposed framework aims to provide cost-effective and real-time anomaly detection using deep neural networks (DNNs) with data collected directly from various indoor environments, where computing resources may be limited.

![figure 1_Framework of the proposed method  Flowchart for outlier detection with a total of 4 paragraphs](https://github.com/rootofdata/LSTM-AE_for_Unsupervised_Outlier_Detection/assets/86711374/2887e153-7702-4e69-8757-a16e77c025e1)

## Process
This introduces an outlier detection method based on an ensemble of LSTM-AE (Long Short-Term Memory Autoencoder) and a sub-algorithm for robust outlier detection in real-world scenarios. The proposed anomaly detection framework comprises four major steps: data cleansing, modeling, decision rule definition, and situational AB test.

#### **1.Data Cleansing (Data Preprocessing):**:
- This step involves extracting and refining sensor-collected data. It focuses on extracting key components for model training, correcting missing values, and addressing outliers generated during data collection.  
- In the data preprocessing stage, normality verification, handling missing values through linear interpolation, and correlation analysis of variables are conducted.

#### **2.Modeling (LSTM-AE)**:
- In this phase, the LSTM-AE model is trained to capture latent features from the data. LSTM-AE is an autoencoder structure that utilizes LSTM layers to learn time-series characteristics in the data. The model is trained to reconstruct the input data and calculate reconstruction errors.
- The modeling stage explains the training of the LSTM-AE model and the conversion of data into a 3D format. It evaluates model performance based on reconstruction error and cluster cohesion, demonstrating the effectiveness of feature learning.

#### **3.Decision Rule Definition**:
- This step involves constructing a sub-algorithm based on the latent features extracted by the encoder of the LSTM-AE. The goal is to define a more accurate and consistent decision-making process for outlier detection. This sub-algorithm complements the reconstruction error-based outlier detection method.
- The extraction of latent features, DBSCAN clustering, and OC-SVM for noise removal in the latent feature space are discussed.

#### **4.Situational AB Test**:
- Laboratory (LAB) tests are conducted to evaluate the performance of the proposed framework under different abnormal situations. These tests involve generating various events to assess outlier detection and model performance objectively.
- The data collected for indoor air quality measurement includes various parameters like PM2.5, PM10, TVOC, CO2, CO, and CH2O, along with temperature and humidity. These data are collected using environmental sensors with different communication methods.
- The extraction of latent features, DBSCAN clustering, and OC-SVM for noise removal in the latent feature space are discussed.

This thesis discusses preprocessing steps, such as time-series data tuning, stationarity checks, handling missing values, and conducting correlation analysis. It also covers the use of clustering techniques (DBSCAN) on latent features and the application of a one-class support vector machine (OC-SVM) for outlier detection in the sub-algorithm.

To create a robust decision rule, the report combines the results from both the reconstruction error-based method and OC-SVM, resulting in a more reliable and accurate outlier detection mechanism.

Finally, It details the LAB tests performed to objectively evaluate the framework's performance under various abnormal scenarios, using data collected from sensor devices. The tests include events like controlled sprays and environmental factor adjustments, with annotations provided for evaluation purposes.

This comprehensive approach aims to address the challenges of unsupervised outlier detection in real-world settings, particularly in the context of indoor air quality monitoring.
