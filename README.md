# solar-energy-prediction-based-on-weather
Project Overview
The Solar Power Prediction Project showcases a machine learning approach for forecasting solar power generation based on weather parameters (e.g., temperature, humidity, wind speed, pressure). The model is trained on a single 655 W LONGi solar panel’s output, and the predicted power is then scaled up to match various system sizes.

Key Objectives:

Provide insights into solar panel specifications (e.g., LONGi 655 W).
Explain how the model leverages daily weather data.
Demonstrate interactive charts and forecasting capabilities.
Generate automated reports using Large Language Models (LLMs).
Features
Single-Panel Training: Trains a regression model on per-panel daily power data.
Dynamic Scaling: Multiplies single-panel output by the number of panels for different system capacities.
Weather Data Integration: Combines temperature, humidity, wind speed, and pressure to forecast output.
Custom Navigation Bar: Uses HTML/CSS to create a fixed top navigation for a website-like feel.
Interactive Visualizations: Utilizes Plotly for dynamic charts.
Automated Reporting: Integrates (or placeholders for) LLMs like OpenAI GPT for summary reports.
Data
Weather Data: Daily maximum, minimum, and average values of temperature, humidity, wind speed, and pressure.
Solar Output Data: Daily power generation from a single solar panel.
A sample row may look like this:

mathematica
Copy code
Date,Temp_Max,Temp_Avg,Temp_Min,Humidity_Max,Humidity_Avg,Humidity_Min,Wind_Speed_Max,Wind_Speed_Avg,Wind_Speed_Min,Pressure_Max,Pressure_Avg,Pressure_Min,Power
20/10/2014,90,80.1,66,83,49.1,29,9,3.8,0,29.2,23.7,0,1603.38754
Getting Started
Prerequisites
Python 3.8+
pip or conda
Virtual environment (recommended)
Installation
Clone the repository:
bash
Copy code
git clone https://github.com/<username>/solar-power-prediction.git
cd solar-power-prediction
Create and activate a virtual environment (example using venv):
bash
Copy code
python -m venv .venv
source .venv/bin/activate       # macOS/Linux
.venv\Scripts\activate          # Windows
Install required packages:
bash
Copy code
pip install -r requirements.txt
Make sure requirements.txt includes libraries like:
python
Copy code
streamlit
pandas
numpy
scikit-learn
plotly
...
Usage
Prepare your data: Place your CSV files (weather data + power data) in a data folder or specify their paths in the code.
Run the Streamlit app:
bash
Copy code
streamlit run app.py
Replace app.py with your actual main Streamlit file.
Open the browser: The console will show a local URL (e.g., http://localhost:8501) where your app is running.
Model
Model Type: You can use any supervised regression model (e.g., Random Forest, XGBoost, Linear Regression).
Target Variable: Daily solar power output (in W or kW) from a single solar panel.
Features: Temp_Max, Temp_Avg, Temp_Min, Humidity_Max, Humidity_Avg, Wind_Speed_Max, ... etc.
Steps:

Data Preprocessing: Handle missing values, outliers, type conversions.
Feature Engineering: Add relevant time-based features (e.g., day of year) if available.
Train-Test Split: Typically 80/20 or time-based for forecasting.
Train and Evaluate using metrics like MAE, RMSE, R².
Scaling Predictions
After training on a single panel, the predicted daily power can be scaled:

Determine the number of panels needed for your chosen system capacity (e.g., 5 kW or 10 kW).
Multiply the single-panel prediction by the number of panels.
Account for real-world losses if desired (inverter efficiency, shade, etc.).
Streamlit App
The app includes:

Navigation Bar: Fixed top bar with links to:

Solar Panel Details
Model Working
Visualizations & Predictions
Reporting
Solar Panel Details: Displays specifications of the LONGi 655 W panel (efficiency, performance, warranty).

Model Working: Explains data sources, model pipeline, and how predictions are generated.

Visualizations & Predictions:

Plots daily power output vs. time.
Shows a correlation heatmap of weather vs. power.
Lets users pick a system size to see total power.
Reporting: Integrates (or placeholders for) an LLM to generate automated performance reports.

License
This project is licensed under the MIT License - see the LICENSE file for details.
If you haven’t set up a license, you can choose one from choosealicense.com.

Thank You!
If you find this project helpful, feel free to star the repository or contribute via pull requests. If you run into any issues, please open a ticket in the Issues section.

