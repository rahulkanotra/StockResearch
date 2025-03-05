Stock Analysis and Forecasting Tool
This project is a Python-based stock analysis and forecasting application that performs both fundamental and technical analysis of stocks. It leverages data from Yahoo Finance, computes various technical indicators, and creates interactive charts using Plotly. The web interface is built using Flask, allowing users to analyze different tickers and chart types.

Features
Data Retrieval:
Fetches historical stock data (and VIX data) from Yahoo Finance using yfinance.

Fundamental Analysis:
Retrieves company information and computes scores based on financial metrics (e.g., P/E ratios, market cap, profitability, etc.).
Provides a detailed printout of key fundamental metrics along with bullish/bearish signals.

Technical Analysis:
Computes various technical indicators such as SMA, EMA, RSI, MACD, Bollinger Bands, ATR, stochastic oscillator, VWAP, Ichimoku Cloud, and ADX.
Scores the technical outlook and detects patterns (e.g., rectangle patterns, double tops/bottoms, breakaway gaps).

Forecasting:
Implements volume forecasting using SARIMAX and price forecasting using Prophet.
Additionally, offers ML-based forecasting for multiple horizons using Random Forest regression.

Chart Generation:
Generates interactive candlestick charts with overlays for moving averages, Bollinger Bands, Fibonacci retracement, and more.

Web Interface:
Provides a Flask-based web application that allows users to enter a ticker symbol and select a chart type (e.g., 1H, 1D, 1W, 1M) for analysis.
Displays both the detailed analysis and an interactive chart on the browser.

Dependencies
The project uses several Python libraries. Ensure you have the following installed:

Data Handling & Analysis:

pandas
numpy
Financial Data & Analysis:

yfinance
talib (TA-Lib for technical analysis indicators)
dateutil
Forecasting & Machine Learning:

statsmodels (for SARIMAX)
prophet (for price forecasting)
scikit-learn (for ML-based forecasts)
Visualization:

plotly
Web Framework:

flask
Utilities:

logging
io
sys
datetime
contextlib
Note: Some libraries (like talib and prophet) may require additional system dependencies. Please refer to their respective installation guides.

Installation
Clone the repository:

bash
Copy
Edit
git clone https://github.com/yourusername/stock-analysis-tool.git
cd stock-analysis-tool
Create and activate a virtual environment (recommended):

bash
Copy
Edit
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
Install the required Python packages:

bash
Copy
Edit
pip install -r requirements.txt
Alternatively, you can manually install the dependencies:

bash
Copy
Edit
pip install pandas numpy yfinance talib plotly statsmodels prophet flask scikit-learn python-dateutil
Usage
Run the Flask App:

Start the web server by running the main script:

bash
Copy
Edit
python <script_name>.py
The app will run on port 5005 (by default). Open your browser and navigate to:

cpp
Copy
Edit
http://127.0.0.1:5005/
Interact with the Web Interface:

Enter a ticker symbol (e.g., TSLA, AAPL, RELIANCE.BO, DMART.NS).
Select the desired chart type from the dropdown (e.g., 1H, 1D, 1W, 1M).
Click Analyze to view the detailed analysis output and interactive chart.
Project Structure
Constants & Configurations:
Constants such as FORECAST_DAYS_MAX and chart horizons are defined at the top.

Helper Functions:
Utility functions for safely parsing values, formatting, and data retrieval.

Scoring Functions:
Functions to compute both original and enhanced fundamental and technical scores.

Technical Indicator Functions:
Functions to calculate key technical indicators (RSI, MACD, Bollinger Bands, etc.).

Pattern Detection & Forecasting:
Implements functions for detecting chart patterns (rectangle, double top/bottom, breakaway gap) and forecasting stock volume and price.

Analysis and Chart Generation:
Functions that generate analysis reports, compute technical/fundamental scores, and create Plotly charts.

Flask Web App:
The Flask app (app) uses a simple HTML template to display the analysis results and chart.

Customization
Forecast Periods & Horizons:
Adjust the constants FORECAST_DAYS_MAX and HORIZONS to change the forecasting window and output intervals.

Indicator Parameters:
Modify parameters (like periods for SMA, RSI, etc.) within the respective functions to fine-tune the analysis.

Styling:
The HTML template in the Flask app can be updated to change the look and feel of the web interface.

Troubleshooting
Data Issues:
If Yahoo Finance does not return any data, ensure that your ticker symbol is valid and that there is sufficient historical data for the requested period.

Library Installations:
Some libraries (like talib and prophet) might require additional steps or system libraries to install correctly. Check their official documentation if you encounter issues.


