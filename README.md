# From Clinical ECGs to Smartwatches: A Translational Machine Learning Approach for Atrial Fibrillation Detection
**Abstract** 
Atrial fibrillation (AF) is one of the most common and underdiagnosed cardiac arrhythmias, contributing significantly to global cardiovascular morbidity. Timely diagnosis is critical to prevent severe outcomes such as stroke. With the proliferation of smartwatches and wearable sensors capable of recording ECG or heart rate variability (HRV), a novel opportunity exists to enable early, passive detection of AF in daily life. In this study, we trained a machine learning model on hospital-based 12-lead ECG data to detect AF and other arrhythmias with high accuracy. While our dataset originates from clinical settings, we argue that the predictive features and model pipeline are directly translatable to data collected via consumer-grade wearables. The high accuracy and class-specific performance suggest strong potential for real-time arrhythmia screening using smartwatches. We propose a framework for deploying this model in wearable devices to support remote cardiac monitoring and reduce AF-related complications.

**Introduction** 
Atrial fibrillation (AF) affects millions globally and significantly elevates the risk of thromboembolic stroke and heart failure. Early detection is vital, particularly for paroxysmal and asymptomatic forms of AF that go unnoticed during routine medical evaluations. Advances in wearable technology, such as smartwatches equipped with ECG and photoplethysmography (PPG) sensors, have enabled continuous, user-friendly heart rhythm monitoring. However, existing algorithms integrated into wearables often lack transparency, are trained on limited proprietary data, or underperform in diverse populations. Our study aims to bridge this gap by leveraging high-quality hospital ECG data to train a robust machine learning classifier capable of detecting AF, with the ultimate goal of embedding this model into wearable platforms for real-world monitoring.

**2. Methods:**
**2.1 Data Source:** 
We used the MIT-BIH Arrhythmia Database, a well-established open-access dataset containing annotated ECG recordings from 47 subjects studied between 1975 and 1979. The dataset includes various rhythm classes such as Normal (N), Atrial Fibrillation (F), Supraventricular Ectopic Beat (SVEB), Ventricular Ectopic Beat (VEB), and a rare Q class.

**2.2 Preprocessing:** 
ECG signals were cleaned, segmented, and encoded. Key features—both time-domain and frequency-domain—were extracted, mimicking those accessible through HRV metrics and single-lead ECG sensors on wearables. To address class imbalance, the Synthetic Minority Oversampling Technique (SMOTE) was applied to increase the representation of minority classes such as AF and SVEB.

**2.3 Model Training:** 
We employed a Random Forest classifier due to its robustness and interpretability. Data were split into training and test sets (80:20), and hyperparameters were optimized using grid search cross-validation. Model performance was assessed via classification report metrics and confusion matrix visualization.

**2.4 Evaluation:** 
The model achieved a 99% overall accuracy on the test set. Performance for AF (F class) detection was particularly strong, with an F1-score of 0.86. SVEB and VEB were also classified with high precision and recall. The Q class, due to its rarity, remained a limitation, which we address in the discussion.

**3. Results:**
•	Overall Accuracy: 99%
•	AF (F) Precision: 0.86
•	AF (F) Recall: 0.85
•	AF (F) F1-Score: 0.86
•	VEB F1-Score: 0.97
•	SVEB F1-Score: 0.91

The confusion matrix revealed minimal overlap between classes, indicating a reliable model with low false positives and negatives across key arrhythmia types. Performance remained strong even for imbalanced classes, thanks to SMOTE augmentation.

 ![image](https://github.com/user-attachments/assets/787c3e4f-664b-4e3c-b547-3aca5a744719)

Figure 1: Conceptual illustration of our proposed smartwatch-based AF detection pipeline. ECG data is collected via hospital settings and used to train a machine learning classifier. The model is then optimized and deployed onto wearable devices such as smartwatches to enable real-time AF detection during daily life.

**4. Discussion:**
Our model demonstrates high accuracy in detecting AF and related arrhythmias using clinical ECG data, and the features extracted align with those obtainable from smartwatches via PPG and single-lead ECG. The novelty of our approach lies in reverse-engineering wearable-ready models from high-quality clinical data—bypassing the need for proprietary wearable datasets.

Although our dataset originates from hospital environments, the underlying feature sets, including RR intervals, waveform morphology, and HRV statistics, are translatable to wearable sensors. This makes our approach immediately applicable to real-world smartwatch deployment, pending validation on wearable-specific datasets. The use of SMOTE ensures that rare classes like AF and SVEB are not overshadowed during model training, further enhancing reliability.
Such a deployment could revolutionize AF screening by enabling silent AF detection in asymptomatic individuals, long-term outpatient rhythm surveillance, and population-level preventive cardiology. The integration of this algorithm into consumer wearables offers an accessible, scalable, and cost-effective solution to combat undiagnosed AF.

**5. Conclusion:**
This study presents a high-performing, interpretable machine learning model for arrhythmia detection trained on hospital ECG recordings. While the data are clinical in origin, our feature engineering and model design are directly compatible with data streams from wearables. We propose a translational pipeline for embedding this classifier into smartwatch platforms, enabling continuous, remote AF monitoring. Future work will focus on validating this model against wearable ECG and PPG data, exploring edge deployment for real-time inference, and integrating user feedback loops for enhanced model adaptability.

**References**
1.	Chugh, S. S. et al. Worldwide epidemiology of atrial fibrillation: a Global Burden of Disease 2010 Study. Circulation 129, 837–847 (2014). 
2.	Natarajan, A. et al. A digital biomarker of diabetes from smartphone-based photoplethysmography and deep learning. NPJ Digit. Med. 5, 1–9 (2022). 
3.	Goldberger, A. L. et al. PhysioBank, PhysioToolkit, and PhysioNet: Components of a new research resource for complex physiologic signals. Circulation 101, e215–e220 (2000). 




