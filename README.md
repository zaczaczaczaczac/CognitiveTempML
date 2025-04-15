# 🧠 Effects of Ambient Temperature on Cognitive Function

This project investigates how different ambient temperatures affect human cognitive performance using EEG data and machine learning techniques. By capturing brainwave patterns with the Muse 2 headband during the Stroop test under different temperature conditions, we analyze, clean, and model the data to evaluate the impact of temperature on mental performance.

## 📌 Project Overview

- **Course**: MANU 465, University of British Columbia  
- **Team Members**: Santiago Mendoza Reyes, Arjav Prasad, Ramiro Bolanos, Sanskar Soni, Yuhan Zeng  
- **Objective**: Use EEG data to determine if colder temperatures impair cognitive function.  
- **Test**: Stroop test under "Room" (~21°C) and "Cold" (~8°C) environments.  
- **Devices**: Muse 2 EEG Headband  

---

## 🧪 Methodology

### 🔹 Data Collection
- Brainwave data collected from UBC students using Muse 2 during Stroop tests.
- Each subject took the test in both "Room" and "Cold" conditions.
- Data types: Alpha, Beta, Gamma brainwaves from 4 EEG sensors.

### 🔹 Data Cleaning & Preprocessing
- Removed NaNs using forward-fill.
- Focused only on **second part** of Stroop test (incongruent stimuli).
- Removed flat or unchanging EEG signals.
- Applied **Fast Fourier Transform (FFT)** to convert time domain to frequency domain.
- Generated features using squared magnitudes of frequency peaks.

### 🔹 Dataset Variants
- Full-recording FFT dataset (60 features).
- 10-second & 8-second sliding FFT window datasets.
- Raw features grouped with 20-timestep windows.
- PCA applied for dimensionality reduction in some variants.

---

## 🤖 Machine Learning Models

| Model                 | Accuracy  |
|----------------------|-----------|
| **XGBoost**          | 88.24% ✅ |
| Random Forest        | 88.24% ✅ |
| Decision Tree        | 76.47%    |
| ANN (Neural Net)     | 76.47%    |
| Logistic Regression  | 64.71%    |
| Naive Bayes          | 64.71%    |
| K-Nearest Neighbors  | 58.82%    |

- Final model of choice: **XGBoost**
- PCA did not improve accuracy and was excluded from final pipeline.

---

## 📊 Key Findings

- EEG brainwave activity (especially Alpha, Beta, Gamma) was lower in colder environments.
- Models consistently distinguish between "Cold" and "Room" conditions.
- **Strong correlation**: Lower temperatures → Lower cognitive performance during Stroop test.

---

## 💡 Applications

- **Workplace**: Optimize office temperatures to maximize productivity.
- **Education**: Enhance learning environments by maintaining ideal temperature ranges.
- **Elderly care**: Adjust environments for improved cognitive health.

---

## 📂 Repository Structure

├── Notebook.ipynb # Data preprocessing, EDA, modeling code ├── Project Report.pdf # Full academic report (with figures, discussion, references) └── README.md # Project documentation (this file)


---

## 🧠 Conclusion

This study confirms that ambient temperature impacts cognitive performance. EEG data, combined with robust cleaning and modeling, revealed that colder temperatures reduce brain activity as measured by the Stroop test. XGBoost emerged as the most reliable model with 88.24% accuracy, and our methodology can serve as a foundation for future research on environmental impacts on cognition.

---

## 📚 References

Key references and data sources are listed in `Project Report.pdf`.

---

© 2024 UBC Integrated Engineering Team | MANU 465 Final Project
