# Cloud Resource Usage Anomaly Detection

## Overview

This project applies exploratory data analysis and machine learning to detect anomalies in cloud resource usage data. Cloud platforms host a wide variety of workloads that continuously consume CPU, memory, disk, and network resources. Identifying abnormal consumption patterns is important for maintaining system reliability, controlling operational cost, and detecting potential misuse of infrastructure.

The project uses a labeled dataset of minute level resource usage records and trains a Random Forest classifier to distinguish between normal and anomalous behavior.

## Dataset

Source: Cloud Resource Usage Dataset for Anomaly Detection (Kaggle)
Link: https://www.kaggle.com/datasets/programmer3/cloud-resource-usage-dataset-for-anomaly-detection
License: CC0-1.0

The dataset contains 14,400 records collected at one minute intervals across 10 users and 5 workload types. Each record includes the following fields:

| Column | Description |
|---|---|
| Timestamp | Date and time of the recorded observation |
| CPU_Usage | Percentage of CPU utilization |
| Memory_Usage | Percentage of memory utilization |
| Disk_IO | Disk input and output activity |
| Network_IO | Network input and output activity |
| Workload_Type | Category of workload being executed |
| User_ID | Identifier of the user associated with the record |
| Anomaly_Label | Binary label, 1 for anomalous and 0 for normal |

## Project Workflow

1. Data loading and inspection
2. Data quality assessment, including detection of invalid negative values
3. Statistical summary of numeric features
4. Visualization of CPU usage over time with anomalies highlighted
5. Comparison of feature averages between normal and anomalous records
6. Analysis of anomaly distribution across workload types
7. Correlation analysis between resource metrics and anomaly labels
8. Feature encoding and train-test split
9. Training a Random Forest classifier
10. Model evaluation using accuracy, precision, recall, and f1-score
11. Confusion matrix visualization
12. Feature importance analysis

## Key Findings

- Anomalies make up approximately 8.7 percent of the dataset
- Anomalies are almost entirely associated with the Crypto_Mining workload type, which accounts for all 1,257 anomalous records
- Average CPU usage rises from about 31 percent in normal records to about 86 percent in anomalous records
- CPU_Usage shows a strong correlation of 0.82 with the anomaly label
- The trained Random Forest model achieved 100 percent accuracy, precision, recall, and f1-score on the test set
- CPU_Usage and Workload_Type together account for over 95 percent of the model's feature importance

## Technologies Used

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Google Colab

## Repository Structure

```
├── Cloud_Resource_Usage_Anomaly_Detection.ipynb   Main analysis notebook
├── Cloud_Resource_Usage_Anomaly_Detection_Report.docx   Detailed project report
├── README.md   Project documentation
```

## How to Run

1. Open the notebook in Google Colab
2. Create a Kaggle API token from your Kaggle account settings and upload the kaggle.json file when prompted
3. Run the notebook cells in sequence to download the dataset, perform the analysis, and train the model

## Author

Muhammad Fiaz
