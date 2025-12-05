**Tourism Smart City Analytics**

This project was developed as part of the Machine Learning: Supervised Techniques course. The goal was to build a small end-to-end analytics system for tourism demand forecasting and event-based recommendations. 
The system focuses on Amsterdam and uses synthetic datasets that cover bookings, events, weather, bus schedules, and web analytics.
Project Overview

The project contains three main components:

**1. Forecasting**
Models city-level demand and RevPAR using Prophet, with additional features such as events and weather. The goal is to estimate short-term tourism trends.

**2. Recommendations**
Generates event recommendations for different types of tourists (personas). The system combines content-based and clustering methods to match people with suitable activities.

**3. Analytics Dashboard**
A Streamlit interface that allows users to explore data, view forecasts, get recommendations, and generate itineraries. The dashboard runs alongside a FastAPI backend
Datasets

All datasets are synthetic and cover the period from December 2023 to February 2026.
They include:

bookings.csv

events.csv

weather.csv

bus_schedules.csv

web_analytics.csv

These datasets are not included in the repository because of size limitations.
They can be recreated using the dataset generator scripts.
To generate all datasets:

`cd mlst/dataset_generators`

`python generate_all_datasets.py`

Running the Project
1. Create and activate a virtual environment:
   
`python -m venv venv`

`source venv/bin/activate` # Linux / macOS

`venv\Scripts\activate `     # Windows

2. Install dependencies:

`pip install -r mlst/requirements.txt`

3. Start the API:

`cd mlst`

`python -m uvicorn api:app --reload --port 8000`

The API will be available at: http://localhost:8000

4. Start the dashboard:

`cd mlst`

`streamlit run dashboard.py --server.port 8501`

The dashboard will be available at: http://localhost:8501

Structure
```

mlst/
    api.py
    dashboard.py
    forecast.py
    recommend.py
    preprocess.py
    personas.py
    config.py
    dataset_generators/
    requirements.txt
```

**Methods Used**

Time series forecasting with Prophet

Feature engineering (event intensity, weather, temporal factors)

Clustering for defining tourist personas

Content-based and hybrid recommendation design

FastAPI backend

Streamlit dashboard UI

**Authors**

Rijalda Sacirbegovic
Almir Mustafic
Benjamin Kljuno



