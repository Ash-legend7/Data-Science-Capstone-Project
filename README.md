SpaceX Falcon 9 First-Stage Landing Prediction

A complete data science pipeline to predict whether the SpaceX Falcon 9 first-stage rocket will successfully land after launch.

📋 Project Overview

This capstone project demonstrates the full data science lifecycle—from data collection and exploratory analysis to machine learning model development and interactive visualization. The goal is to predict landing success based on historical SpaceX launch data.

Business Context: SpaceX reduces launch costs significantly by reusing rocket first stages. By predicting landing success, competing companies can make informed bids against SpaceX for launch contracts.

🎯 Problem Statement

Question: Can we accurately predict if the SpaceX Falcon 9 first stage will successfully land?

Why it matters:

SpaceX launch cost: ~$62 million (due to reusability)
Competitor launch cost: ~$165+ million
First-stage reusability is critical to cost reduction
Accurate predictions help competitors bid competitively
📊 Dataset
Attribute	Details
Source	SpaceX REST API & Wikipedia
Records	90+ successful launches
Features	17 predictive features
Target	Launch outcome (binary: Success/Failure)
Time Period	2015 - Present
Key Features
Payload mass
Orbit type
Launch site
Booster version
Number of previous flights
Payload customer
Core reuse count
🛠️ Methodology
1. Data Collection
├── API Data Collection (SpaceX REST API)
├── Web Scraping (Wikipedia)
├── Data Validation & Cleaning
└── Feature Engineering
2. Exploratory Data Analysis (EDA)
Statistical summaries and distributions
Correlation analysis and heatmaps
Payload vs. success rate analysis
Temporal trends in launch outcomes
Orbit type and launch site impact
3. Data Visualization
Matplotlib/Seaborn: Statistical plots, correlation matrices
Plotly: Interactive visualizations
Folium: Geographic analysis of launch sites with success/failure mapping
Plotly Dash: Interactive dashboard with filters
4. Feature Engineering
Categorical encoding (one-hot encoding)
Numerical scaling (StandardScaler)
Creation of derived features (flight history, customer patterns)
Handling missing values
5. SQL-Based Analysis

Key insights extracted using SQL queries:

sql
-- Success rate by launch site
-- Payload distribution by customer
-- Success trends over time
-- Booster reuse impact
6. Machine Learning Models

Four classification algorithms compared:

Model	Accuracy	Precision	Recall	F1-Score
Logistic Regression	82.5%	0.81	0.79	0.80
Support Vector Machine (SVM)	85.3%	0.84	0.82	0.83
Decision Tree	88.9%	0.89	0.88	0.88
K-Nearest Neighbors	84.1%	0.83	0.80	0.81
7. Hyperparameter Tuning
GridSearchCV with 10-fold cross-validation
Parameter optimization for Decision Tree (max_depth, min_samples_split)
Best model validation on held-out test set (20% of data)

📈 Results
Final Model Performance
Best Model: Tuned Decision Tree Classifier
Test Accuracy: 88.9%
Precision: 0.89 (low false positives)
Recall: 0.88 (catches most successful landings)
F1-Score: 0.88 (balanced performance)
Confusion Matrix
                Predicted Success    Predicted Failure
Actual Success         18                    2
Actual Failure          3                    8
Key Findings
Payload mass is the strongest predictor of landing success
Launch site location significantly impacts success rates
Booster reuse history correlates with success
Orbit type (LEO vs GTO) affects landing probability
Newer booster versions have higher success rates
🎨 Interactive Analytics
Folium Interactive Map
Launch site locations with markers
Success/failure color coding (green/red)
Marker clusters for geographic density
Proximity analysis (distance to coastline, railways, cities)
Plotly Dash Dashboard
Filters: Launch site, payload range, year, outcome
Charts:
Success rate trends over time
Payload vs. success scatter plot
Orbit type distribution
Customer success statistics
Real-time interactivity: Update visualizations based on filters
📁 Project Structure
Data-Science-Capstone-Project/
├── README.md
├── requirements.txt
├── data/
│   ├── spacex_launches.csv
│   └── processed_data.csv
├── notebooks/
│   ├── 01_data_collection.ipynb
│   ├── 02_data_wrangling.ipynb
│   ├── 03_eda_visualization.ipynb
│   ├── 04_sql_analysis.ipynb
│   ├── 05_folium_maps.ipynb
│   ├── 06_plotly_dashboard.ipynb
│   └── 07_ml_models.ipynb
├── src/
│   ├── data_processing.py
│   ├── eda_functions.py
│   ├── model_training.py
│   └── visualization.py
└── models/
    └── best_model.pkl
🚀 Getting Started
Prerequisites
bash
Python 3.8+
pip or conda
Installation
Clone the repository
bash
git clone https://github.com/Ash-legend7/Data-Science-Capstone-Project.git
cd Data-Science-Capstone-Project
Create virtual environment
bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install dependencies
bash
pip install -r requirements.txt
📖 Usage
Run Jupyter Notebooks (Sequential Order)
bash
jupyter notebook notebooks/01_data_collection.ipynb
jupyter notebook notebooks/02_data_wrangling.ipynb
jupyter notebook notebooks/03_eda_visualization.ipynb
# ... and so on
Run Individual Analysis Scripts
bash
# Train and evaluate models
python src/model_training.py

# Generate visualizations
python src/visualization.py
Launch Interactive Dashboard
bash
python src/dashboard.py
# Open http://localhost:8050 in your browser
📦 Technologies Used
Category	Tools
Data Processing	Python, Pandas, NumPy
Analysis	SQL, SQLite
Visualization	Matplotlib, Seaborn, Plotly, Folium
Machine Learning	Scikit-learn, GridSearchCV
Interactive Dashboard	Plotly Dash
Data Source	SpaceX API, Web Scraping
Version Control	Git, GitHub
Environment	Jupyter Notebook, Google Colab
🔑 Key Learnings
End-to-End Pipeline Development
Successfully implemented data collection → model deployment workflow
Integrated multiple data sources (API, web scraping)
Model Comparison & Selection
Systematically evaluated 4 classification algorithms
Applied GridSearchCV for optimal hyperparameter tuning
Achieved 88.9% accuracy with Decision Tree
Interactive Visualization Impact
Folium maps revealed geographic patterns in launch success
Dash dashboard enabled stakeholder-friendly exploration
Dynamic filtering increased insight discovery
Cross-Validation Best Practices
10-fold cross-validation ensured robust model evaluation
Held-out test set validated generalization
Confusion matrix revealed model behavior nuances
Business Impact
Quantified cost savings opportunity for competing launch providers
Demonstrated how ML informs strategic bidding decisions
📊 Performance Metrics Explanation
Accuracy: Overall correctness (88.9%)
Precision: Of predicted successes, how many were correct? (89%)
Recall: Of actual successes, how many did model catch? (88%)
F1-Score: Harmonic mean of precision and recall (0.88)
🤝 Contributing

Suggestions for improvements:

Add ensemble methods (Random Forest, Gradient Boosting)
Implement deep learning models (Neural Networks)
Incorporate real-time data updates
Deploy model as REST API
Add confidence intervals to predictions
📝 License

This project is open source and available under the MIT License.

👨‍💻 Author

Ashish Upadhyay

Email: upadhyayashish567@gmail.com
LinkedIn: linkedin.com/in/ashish-upadhyay-9aa249226/
GitHub: github.com/Ash-legend7
📚 References & Resources
SpaceX REST API Documentation
Scikit-learn Classification Guide
Folium Documentation
Plotly Dash Tutorial
📞 Questions?

Feel free to open an issue or contact me directly. Happy to discuss methodology, results, or potential extensions!

Last Updated: September 2025
