# SIH1647: AI-ML Based Price Prediction for Agri-Horticultural Commodities

## Overview
This project predicts the prices of Onion, Potato, and Tomato using a hybrid approach. It combines traditional time-series models (ARIMA, Random Forest, Prophet) with an **LLM-Weighted Dynamic Ensemble**. 

## Innovative Algorithm
Unlike standard models, this project uses a Large Language Model (LLM) via the Groq API. The LLM analyzes live data (last 5 days prices + model forecasts) and generates an optimized prompt to assign dynamic weights to ARIMA, Random Forest, and Prophet. This ensures the ensemble adapts to real-time market conditions.

## Setup
1. Install requirements: `pip install -r requirements.txt`
2. Set your Groq API key as an environment variable: `GROQ_API_KEY="gsk_..."`

## Data
The data is sourced from the Kaggle dataset: "Indian Agricultural Mandi Prices (2023–2025)".

## Results
| Crop | ARIMA MAPE | RF MAPE | Prophet MAPE | Best Model | LLM Weights |
|---|---|---|---|---|---|
| Onion | 14.70% | **5.43%** | 26.71% | Random Forest | ARIMA: 0.6, RF: 0.3, Pro: 0.1 |
| Potato | 8.20% | **4.95%** | 16.43% | Random Forest | ARIMA: 0.45, RF: 0.35, Pro: 0.2 |
| Tomato | **16.64%** | 20.78% | 1336.10% | ARIMA | ARIMA: 0.7, RF: 0.3, Pro: 0.0 |

*Note: Prophet failed on Tomato due to limited data (154 data points).*
