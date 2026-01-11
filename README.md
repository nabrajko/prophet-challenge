# Prophet Challenge - MercadoLibre Search Traffic Analysis

A time series analysis project using Facebook Prophet to analyze Google search traffic patterns for MercadoLibre and explore correlations with stock price movements to predict trading opportunities.

## Project Overview

As a growth analyst at MercadoLibre (Latin America's largest e-commerce platform with 200+ million users), this project investigates whether Google search traffic patterns can predict stock trading success. The analysis combines search traffic data, stock price patterns, and time series forecasting to generate actionable business insights.

## Business Objective

Determine if the ability to predict search traffic can translate into successful stock trading strategies by:
- Identifying unusual patterns in search traffic
- Mining seasonal trends in user interest
- Correlating search behavior with stock price movements
- Forecasting future search traffic patterns

## Technologies Used

- **Python**: Primary programming language
- **Facebook Prophet**: Time series forecasting
- **Pandas**: Data manipulation and analysis
- **Matplotlib/Plotly**: Data visualization
- **Jupyter Notebook**: Interactive development environment

## Project Structure

The analysis is divided into four main steps:

### Step 1: Find Unusual Patterns in Hourly Google Search Traffic

**Objective**: Determine if Google search traffic correlates with financial events or represents random noise.

**Tasks**:
- Read search data into a DataFrame
- Slice data to May 2020 (when MercadoLibre released quarterly financial results)
- Visualize the data to identify unusual patterns
- Calculate total search traffic for May 2020
- Compare May traffic to monthly median across all months
- Analyze if search traffic increased during financial results release

### Step 2: Mine the Search Traffic Data for Seasonality

**Objective**: Identify predictable seasonal patterns to optimize marketing efforts and ROI.

**Tasks**:
- **Hourly Analysis**: Group data to plot average traffic by hour of day
  - Determine if search traffic peaks at specific times
- **Daily Analysis**: Group data to plot average traffic by day of week
  - Identify busiest days (e.g., Monday vs. Friday)
- **Weekly Analysis**: Group data to plot average traffic by week of year
  - Analyze if traffic increases during winter holiday period (weeks 40-52)
- Document time-based trends and patterns

### Step 3: Relate the Search Traffic to Stock Price Patterns

**Objective**: Investigate relationships between search data and stock price movements.

**Tasks**:
- Import and plot stock price data
- Concatenate stock price data with search data into single DataFrame
- Analyze first half of 2020 (2020-01 to 2020-06):
  - Examine if both time series show consistent trends during COVID-19 market disruption
  - Validate narrative of e-commerce platform growth post-initial shock
- Create derived features:
  - **Lagged Search Trends**: Search traffic offset by one hour
  - **Stock Volatility**: Exponentially weighted 4-hour rolling average
  - **Hourly Stock Return**: Percent change in stock price per hour
- Analyze predictable relationships between:
  - Lagged search traffic and stock volatility
  - Lagged search traffic and stock price returns

### Step 4: Create a Time Series Model with Prophet

**Objective**: Build forecasting model to predict search traffic patterns.

**Tasks**:
- Prepare Google search data for Prophet model
- Train and estimate the Prophet model
- Generate and plot forecasts
- Analyze near-term popularity forecast for MercadoLibre
- Examine individual time series components to answer:
  - What time of day exhibits the greatest popularity?
  - Which day of the week gets the most search traffic?
  - What's the lowest point for search traffic in the calendar year?

## Key Analysis Questions

1. **Financial Events Impact**: Does Google search traffic increase during earnings releases?
2. **Hourly Patterns**: When do users search most frequently throughout the day?
3. **Weekly Trends**: Which days drive the highest engagement?
4. **Seasonal Variations**: Does search interest spike during holiday periods?
5. **Stock Correlation**: Can search patterns predict stock volatility or returns?
6. **Future Trends**: What does the forecast indicate for near-term popularity?

## Dataset

- **Google Search Traffic Data**: Hourly search trends for MercadoLibre
- **Stock Price Data**: Historical stock prices and trading information
- **Time Period**: 2020 (with focus on May 2020 financial results and first half analysis)

## Getting Started
```python
import pandas as pd
from prophet import Prophet
import matplotlib.pyplot as plt

# Load search traffic data
df_search = pd.read_csv('google_hourly_search_trends.csv')

# Load stock price data
df_stock = pd.read_csv('mercado_stock_price.csv')

# Prepare data for Prophet
df_prophet = df_search.rename(columns={'Date': 'ds', 'Search_Trends': 'y'})
```

## Key Skills Demonstrated

- Time series analysis and forecasting
- Facebook Prophet implementation
- Seasonal decomposition
- Feature engineering (lagged variables, rolling averages)
- Stock market correlation analysis
- Data visualization and pattern recognition
- Business intelligence and actionable insights generation

## Expected Insights

- Identification of optimal marketing times based on search patterns
- Understanding of search traffic seasonality
- Correlation between user interest and stock performance
- Predictive capabilities for future search trends
- Strategic recommendations for marketing budget allocation

## Results Interpretation

The analysis provides actionable insights for:
- **Marketing Team**: Optimal timing for campaigns based on peak traffic periods
- **Finance Team**: Understanding relationship between search interest and stock performance
- **Executive Leadership**: Forecasting user engagement and platform popularity
- **Investors**: Potential trading signals based on search traffic patterns

