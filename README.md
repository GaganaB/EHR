# Patient Selection for Diabetes Drug Testing Project

EHR data is becoming a key source of real-world evidence (RWE) for the pharmaceutical industry and regulators to make decisions on clinical trials. We are herewith building a predictive model that can identify which type of patients to test drugs on. Target patients are assumed to be likely to be in the hospital for this duration of time and will not incur significant additional costs for administering this drug to the patient and monitoring.

We first build a regression model that can predict the estimated hospitalization time for a patient and also provide an uncertainty estimate range for that prediction so that predictions can be ranked based off of the uncertainty range.

## Expected Hospitalization Time Regression and Uncertainty Estimation Model: 
We are utilizing a synthetic dataset(upsampled, denormalized, with line level augmentation) built off of the UCI Diabetes readmission dataset (https://archive.ics.uci.edu/ml/datasets/diabetes). 

## Dataset:
Due to healthcare PHI regulations (HIPAA, HITECH), there are limited number of publicly available datasets and some datasets require training and approval. So, for the purpose of this exercise, we are using a dataset from UC Irvine that has been modified for this course. Please note that it is limited in its representation of some key features such as diagnosis codes which are usually an unordered list in 835s/837s (the HL7 standard interchange formats used for claims and remits).

https://archive.ics.uci.edu/ml/datasets/Diabetes+130-US+hospitals+for+years+1999-2008 Data Schema The dataset reference information can be https://github.com/udacity/nd320-c1-emr-data-starter/tree/master/project/data_schema_references. There are two CSVs that provide more details on the fields and some of the mapped values.

This project demonstrates the importance of building the right data representation at the encounter level, with appropriate filtering and preprocessing/feature engineering of key medical code sets which also requires analysis and interpretation of the model for biases across key demographic groups. Lastly, we provide uncertainty range estimates in the regression output predictions to prioritize and triage prediction uncertainty levels.

This demographic bias analysis detects if the proposed model has any bias which we know can be a huge issue in working with healthcare data! 

## Algorithm:


    Data Analysis
    Create Categorical Features with TF Feature Columns
    Create Continuous/Numerical Features with TF Feature Columns
    Build Deep Learning Regression Model with Sequential API and TF Probability Layers
    Evaluating Potential Model Biases with Aequitas Toolkit
    

