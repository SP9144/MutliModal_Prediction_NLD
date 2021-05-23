# **Prediction of Parkinson’s Disease using Multimodality based Machine Learning Methods**


## **Motivation**

Parkinson's disease (PD) is a brain disorder that leads to shaking, stiffness, and difficulty with walking, balance, and coordination. Parkinson's symptoms usually begin gradually and get worse over time. As the disease progresses, people may have difficulty walking and talking. 
More than 10 million people worldwide are living with PD. Incidence of Parkinson's disease increases with age, but an estimated four percent of people with PD are diagnosed before age 50. 
 

## **Dataset**

We are using the PPMI dataset [[PPMI]](https://www.michaeljfox.org/news/parkinsons-progression-markers-initiative-ppmi) available on the LONI database hosted by UCLA. As of today, the data set contains longitudinal data, including clinical, imaging and genetic data, of over 700 participants.
* Healthy Controls (HC) = 213
* Parkinson's Disorder (PD) = 503

### Clinical Data

Here, 682 participants were analyzed with,
* HC = 196
* PD = 486

The following features were considered for clinico-demographic analysis, namely, First Fam Num, First Fam PD, Other Fam Num, Other Fam PD, AGE, So-cio Score, BJLO, ESS, GDS, HVLT RECALL, HVLT RECOG, HVLT RETENT, LNS, QUIP SEC A, QUIP SEC B, QUIP SEC C, QUIP SEC D, QUIP SEC E, RBDSQ, SCOPA TOTAL, SCOPA GASTRO, SCOPA URINARY, SCOPA CARDIO, SCOPA THERMO, SCOPA PUPIL, SCOPA SEXUAL, SFT, STAI, and UPSIT. A detailed description of the various parameters and their computations is listed in Supplementary Table 1.

### Biospecimen Data

For the biospecimen modality, 641 participants were analyzed, with,
* HC = 185
* PD = 456

The features considered were Aβ42, αSYN, P TAU, T TAU, and URATE obtained from the cerebrospinal fluid of the participant.

### Genetic Data

We considered 733 participants, with
* HC = 217
* PD = 516

Here, we use SNP data of 733 different patients. Each patient has his/her own SNP data in the form of an individual Variant Calling Format (VCF) file. We preprocess all tis data to generate one common binary matrix. From 6899 unique SNPs, we shortlisted 93 prognostic SNPs using a biology-based approach followed by XGBoost for further filtering.


## **Methods**

We built predictive models using supervised machine learning for PD diagnosis using the three data modalities individually and then on the combined multi-modal data using an early integration method. Exploratory data analysis was also done. For each of the data types, we trained:
* Random Forest classifiers
* Gaussian Naive Bayes
* Support Vector Machines (SVM)
* Logistic Regression
* Stochastic Gradient Descent classifier (SGD)
* Artificial Neural Networks (ANN)

To train the different models, we performed a Randomized Search over the tunable hyperparameters and performed a 5-fold Cross-Validation to further validate our results.


*All results have been compiled and present in the Report. Code relating to the trained models, including the models and their weights are present in the ```train_code``` folder.*
