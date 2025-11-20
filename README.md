# Global YouTube Trending Analysis & Viral Prediction  
### *Break Through Tech AI Studio — Independent Project by Nancy Kwak*

---

## 🎯 Project Highlights

- Built a global-scale ML system using **2.9M+ YouTube Trending records** across **11 countries**.  
- Developed a unified **viral classification model** achieving **ROC-AUC = 0.998** with strong recall.  
- Engineered advanced **time-based** and **engagement-velocity** features showing how engagement *speed* drives virality.  
- Performed **region-level modeling** (Americas, Europe, Asia) to study market-specific content behavior.  
- Built a regression model to predict **time-to-trending** (algorithmic lift speed).  
- Conducted **deep error analysis**, uncovering slow-burn virality, late-trending patterns, and unexpected viral events.  
- Generated insights for understanding **algorithmic amplification**, audience behavior, and global content ecosystems.

---

## 👩🏽‍💻 Setup & Installation

```bash
# Clone this repository
git clone https://github.com/nancy1404/youtube-trending-analysis.git
cd youtube-trending-analysis

# (Optional) Create environment
python3 -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook

## 📁 Datasets
**Download the data:**
    *   Acquire the dataset from [Kaggle](https://www.kaggle.com/datasets/rsrishav/youtube-trending-video-dataset) and place the CSV files in a `data/` directory.
    
Place the 11 YouTube Trending CSV files inside a folder named **`datasets/`**.

---

# 🏗️ Project Overview

This project was originally built within the **Break Through Tech AI Studio** initiative and expanded into a fully independent, research-grade global analysis.

## ❓ Core Question  
**Why do some videos go viral — and how quickly do they trend across different global markets?**

## 🌍 What This Project Includes
- A unified **ML pipeline** for viral classification  
- Analysis of **engagement velocity** (likes/hour, comments/hour)  
- Modeling of **algorithmic trending speed**  
- **Cross-country** and **regional** comparative analysis  
- Detection of **market differences** in algorithmic uplift  
- Full **error analysis** of false positives and false negatives  

### 🔧 Technologies Used
- **pandas**
- **scikit-learn**
- **matplotlib**
- **seaborn**
- **xgboost**

---

# 📊 Data Exploration

## 📁 Dataset Summary

| Property | Details |
|----------|---------|
| **Rows** | ~2.9M |
| **Countries** | 11 |
| **Features** | Engagements, metadata, timestamps |
| **Engineered Features** | time-to-trending, velocity metrics, metadata richness |

---

## 🔧 Preprocessing & Feature Engineering

### **Time-based Features**
- `publish_hour`  
- `publish_dayofweek`  
- `days_to_trending`  
- `hours_to_trending`  

### **Metadata Features**
- `title_length`  
- `tag_count`  

### **Engagement Velocity (KEY)**
- `likes_per_hour`  
- `comments_per_hour`  
- `engagement_per_hour`  

---

## 🧭 Key EDA Insights

- Viral videos exhibit **5×–7× higher engagement velocity** than non-viral ones.  
- Countries like **KR, RU, IN** trend significantly faster than **US, CA, GB**.  
- Some categories trend at **different speeds** depending on country & audience.  
- Trending is strongly correlated with **early viewer momentum**, not raw totals.  

---

# 🧠 Model Development

## Models Implemented
- **Logistic Regression**  
- **Random Forest Classifier**  
- **XGBoost Classifier**  
- **Naive Bayes**  
- **Random Forest Regressor** (for trending speed)  

---

## Preprocessing Pipeline

Using **ColumnTransformer**:
- `OneHotEncoder` for country & category  
- `StandardScaler` for numeric variables  

---

## Evaluation Metrics

- **Accuracy**  
- **Precision**  
- **Recall**  
- **F1 Score**  
- **ROC-AUC** (primary metric)  
- **Regression:** MAE, RMSE, R²  

---

## 🏆 Performance Summary

- **Best model:** Random Forest  
- **ROC-AUC:** 0.996–0.998 globally  
- Americas & Europe → **nearly perfect performance**  
- Asia → slightly lower recall due to **late-trending dynamics**  

---

# 📈 Results & Key Findings

## 🔥 1. Viral prediction is extremely accurate globally
- Early **likes & comments** dominate predictive power  
- Metadata adds moderate signal  
- Country-level patterns reveal unique content behavior  

---

## 🔥 2. Trending speed varies massively by country

| Fast Trending | Moderate | Slow Trending |
|---------------|-----------|----------------|
| **KR, RU, IN** | **FR, DE, GB** | **US, CA, MX, BR, JP** |

These differences reflect cultural habits and algorithmic thresholds.

---

## 🔥 3. Engagement velocity is the strongest signal

Viral videos typically have:
- **6,616 likes/hour**
- **7× higher comment velocity**
- Steep velocity distributions compared to non-viral videos

➡️ **Velocity > Raw counts**

---

## 🔥 4. Regression model reveals trending latency

- **MAE:** 1.79 days  
- **R² ≈ 0.33** (reasonable given platform randomness)  
- Trending speed depends more on **metadata richness** than virality  

---

## 🔥 5. Error analysis uncovers important behavior patterns

### **False Positives**
High early engagement but *fail* to trend  
(especially common in **IN, MX, RU**)

### **False Negatives**
Slow-burn videos that eventually trend due to:
- news cycles  
- external promotion  
- creator fanbase surges  

These reveal:
- **algorithm-driven thresholds**
- missing features like subscriber count & 12-hour engagement curves  

---

# 🚀 Next Steps (Future Work)

### Potential Extensions:
- Add **BERT-based NLP** for multilingual titles/descriptions  
- Use **RNN / TCN / LSTM** for temporal engagement modeling  
- Build **graph models** for related-video diffusion  
- Add **multilingual topic modeling**  
- Use **SHAP** for global explainability  
- Predict **future peak views**, not just virality  

---

# 📁 Repository Structure (Recommended)

```plaintext
/notebooks
    Global_Notebook.ipynb
    BR_Notebook.ipynb
    CA_Notebook.ipynb
    DE_Notebook.ipynb
    FR_Notebook.ipynb
    GB_Notebook.ipynb
    JP_Notebook.ipynb
    KR_Notebook.ipynb
    MX_Notebook.ipynb
    IN_Notebook.ipynb
    RU_Notebook.ipynb
    US_Notebook.ipynb

/datasets
    <11 CSV files here>

/src
    utils.py
    preprocessing.py
    models.py

README.md
requirements.txt
