# Early Detection and Differential Diagnosis of Alzheimer’s Disease

This project explores using sequential lab-test history to detect Alzheimer’s Disease (AD) early and differential diagnosis of alzheimer's disease. Specifically, we focus on using widely available general lab-test results, which are often taken as routine screenings, as a more accessible basis for diagnosis compared to more specialized and late-stage tests like cerebrospinal fluid (CSF) analysis or PET scans.


## Introduction
Many diseases, such as dementia, have a prolonged progression that makes early detection complex. For Alzheimer’s Disease, the most common cause of dementia, the challenge is heightened due to overlaps in symptoms with other causes like Parkinson’s disease, vascular dementia, or even reversible factors like vitamin deficiencies. Misdiagnosis not only risks incorrect treatment but also delays effective interventions.

Traditional diagnostic methods often rely on specialized tests that are not routinely available and can only be taken after symptoms have progressed. This limits early AD detection and diagnosis. Our approach addresses these limitations by leveraging sequential lab-test histories, which are routinely collected in electronic health records, as an effective tool for detecting and diagnosing AD. 

The primary objectives of our research are:
1. **To capture the temporal relationships within patients' routine lab-test histories using embedding techniques.**
2. **To develop a classification model that uses lab-test sequences for early AD detection and differential diagnosis, minimizing the reliance on specialized tests.**

## Methodology
### Early Detection vs. Diagnosis
Early detection uses general lab-test data available before AD-specific tests, while diagnosis relies on a complete set of diagnostic tests.

### General vs. Specialized Lab Tests
Our approach emphasizes widely accessible general lab tests, aiming to create a tool not reliant on specialized procedures.

### Dementia Cohort Phenotyping
We selected dementia patients from the MIMIC database based on standardized ICD codes, yielding a diverse cohort for early detection and diagnosis.

### Lab-Test History Embedding
We embedded lab-test histories with `word2vec`(`BERT` were also tested), reduced dimensions with PCA, and used t-SNE for visualization, capturing key sequential features.

### Classification Models

#### Baseline Models
We used traditional binary classification models (Logistic Regression, Decision Tree, and Random Forest) as benchmarks. Each patient was represented by a vector containing lab-test results, with missing values filled using cohort-based means or medians.

#### Our Approach: Sequential Models
Inspired by Natural Language Processing techniques, we used LSTM to process lab-test history as sequential data, capturing temporal patterns that could indicate AD progression. Time gaps between test admissions were embedded in the input vectors to enhance temporal precision.

To ensure robustness, we also experimented with alternative models such as GRU and Transformer-based models, available in the `experiment` folder. These models allowed us to compare different architectures for processing sequential data and identify the most effective structure.


## Experiment Folder
The `experiment` folder contains the code for the different models we tested, including Transformer, GRU, and other variants. Each script in this folder is an implementation of a unique model setup or experimental adjustment, allowing comparisons across methods.


---
