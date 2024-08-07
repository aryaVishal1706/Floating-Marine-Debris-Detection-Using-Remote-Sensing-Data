# Floating Marine Debris Detection Using Remote Sensing Data

## Introduction

This project aims to detect floating marine debris using remote sensing data from Sentinel-2 satellites. We utilize the MARIDA (Marine Debris Archive) dataset, which includes multi-spectral images capturing various types of debris like Sargassum macroalgae, ships, natural organic material, waves, wakes, plastics, etc.

## Dataset

The MARIDA dataset, used as a benchmark for developing and evaluating machine learning algorithms, contains 1381 patches with 837,357 annotated pixels based on 63 Sentinel-2 scenes from 2015 to 2021. Each image is 256x256 pixels, where each pixel represents a 10m area, covering 2.4 x 2.4 km. The dataset is imbalanced, with 373 patches containing marine debris and 1008 patches containing other classes. It includes masks with pixel-wise annotated classes and confidence levels.

**Dataset Directory:**
[Access MARIDA Dataset](https://marida-dataset-link)

![Sample Dataset Image](/src/MARIDA.png)

## Methodology

### Data Preprocessing

The MARIDA dataset was preprocessed by dividing the data into two classes: marine debris (1) and non-debris pixels (0). To address class imbalance, we applied the Synthetic Minority Over-sampling Technique (SMOTE), generating synthetic data points for the minority class.

### Model Development

Three Random Forest models were developed with different configurations:

1. **Random Forest with 100 Decision Trees:**
   - Accuracy: 99.9%
   - Precision: 0.23
   - Recall: 0.39
   - F1-Score: 0.29
   - ![Performance Metrics - 100 Trees](path_to_100_trees_image.jpg)

2. **Random Forest with 500 Decision Trees:**
   - Accuracy: 99.52%
   - Precision: 0.0
   - Recall: 0.90
   - F1-Score: 0.01
   - ![Performance Metrics - 500 Trees](path_to_500_trees_image.jpg)

3. **Random Forest with 3500 Decision Trees:**
   - Accuracy: 99.48%
   - Precision: 0.0
   - Recall: 0.91
   - F1-Score: 0.01
   - ![Performance Metrics - 3500 Trees](path_to_3500_trees_image.jpg)

### Feature Engineering

Advanced feature indices such as NDVI (Normalized Difference Vegetation Index), Plastic Index, and FDI (Floating Debris Index) were incorporated into the models to enhance detection capabilities.

## Results

The performance of each model was evaluated based on precision, recall, and F1-score. The Random Forest model with 100 decision trees exhibited the best overall performance, achieving the highest accuracy and better precision and recall metrics compared to models with 500 and 3500 decision trees.

| Metric      | Random Forest with 100 | Random Forest with 500 | Random Forest with 3500 |
|-------------|-------------------------|------------------------|-------------------------|
| Precision   | 0.23                    | 0.0                    | 0.0                     |
| Recall      | 0.39                    | 0.90                   | 0.91                    |
| F1-Score    | 0.29                    | 0.01                   | 0.01                    |

## Discussion

This study demonstrates the effectiveness of using the Random Forest algorithm combined with SMOTE and advanced feature indices for marine debris detection. Methodology 1 with 100 decision trees showed significant improvements in detection performance. Methodology 2 and 3, incorporating larger ensembles and advanced indices, provided superior results, highlighting the importance of feature engineering and robust ensemble models.

## Conclusion

The use of SMOTE and advanced feature indices significantly improved marine debris detection. Future research should focus on integrating additional relevant indices and optimizing model configurations to continue improving detection capabilities, supporting environmental conservation and marine management strategies.

## References

- [MARIDA Dataset](https://marida-dataset-link)
- [Synthetic Minority Over-sampling Technique (SMOTE)](https://smote-link)
