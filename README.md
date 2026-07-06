# ⚡ LoashedPK — Pakistan Load Shedding Predictor

A machine learning-powered dashboard that predicts the probability of electricity load shedding (outages) for the next 24 hours, city-wise across Pakistan.

## 📌 Overview

LoashedPK uses a **Random Forest Classifier** trained on realistic load-shedding patterns (based on NEPRA-style seasonal and hourly trends) to predict hour-by-hour outage risk for major Pakistani cities. Results are displayed through an interactive **Streamlit dashboard**.

## 🎯 Problem Statement

Load shedding in Pakistan varies by city, season, and time of day. This tool predicts when outages are most likely, helping users plan around it.

## ⚙️ Tech Stack

- **Python**
- **Streamlit** — interactive dashboard
- **Scikit-learn** — Random Forest / Gradient Boosting classifier
- **Pandas / NumPy** — data handling
- **Plotly** — visualizations

## 🧠 Features Used

- Hour of day
- Day of week
- Month & season
- City (encoded)
- Weekend flag
- Peak hours flag (6–9 AM, 2–6 PM)
- Temperature proxy (summer = higher demand)

## 🏙️ Cities Covered

Lahore, Rawalpindi, Faisalabad, Multan, Gujranwala, Sialkot, Bahawalpur — each with its own outage severity profile.

## 🔄 How It Works

1. User selects a **city** and **date** from the sidebar
2. The trained Random Forest model predicts outage probability for each of the next 24 hours
3. An adjustable **threshold slider** lets users control sensitivity (probability above threshold = outage predicted)
4. Results are visualized as an interactive hourly risk chart

## 📂 Project Structure

```
ml_predictor/
├── ml_app.py              # Streamlit dashboard (UI + visualization)
├── model.py                # Model training, data generation & prediction logic
├── loadshedding_model.pkl   # Trained Random Forest model
├── city_encoder.pkl         # Label encoder for city names
└── requirements.txt          # Dependencies
```

## 🚀 How to Run

```bash
pip install -r requirements.txt
streamlit run ml_app.py
```

## 📊 Results

The model achieves approximately **77% accuracy** in predicting outage risk windows, with the strongest patterns around afternoon peak hours (2–6 PM) and summer months.

## ⚠️ Note

Training data is synthetically generated based on realistic city/hour/season patterns rather than live NEPRA data — this is a prototype demonstrating the ML pipeline, not a live production forecasting service.

## 👩‍💻 Author

**Alishba Nadeem**
BS Artificial Intelligence, NUML Islamabad
[GitHub](https://github.com/Alishba-Nadeem1) · [LinkedIn](https://linkedin.com/in/alishba-nadeem-8014b9379)
