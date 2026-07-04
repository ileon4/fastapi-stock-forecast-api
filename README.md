# FastAPI Stock Forecast API

A machine learning API built with **FastAPI** that forecasts stock prices using the **Prophet** time series forecasting library. The application downloads historical stock market data from Yahoo Finance, trains a forecasting model, and serves predictions through a REST API.

This project was built as a hands-on introduction to deploying machine learning models with FastAPI and demonstrates how to expose a trained model through an HTTP endpoint.

---

## Features

* Train a stock forecasting model using Prophet
* Download historical stock data with yfinance
* Serve predictions through a FastAPI REST API
* Validate incoming requests with Pydantic
* Return predictions as JSON
* Interactive API documentation with Swagger UI

---

## Tech Stack

* Python
* FastAPI
* Pydantic
* Prophet
* Pandas
* yfinance
* Uvicorn

---

## Project Structure

```text
fastapi-ml/
│
├── main.py            # FastAPI application and API routes
├── model.py           # Machine learning logic
├── requirements.txt   # Project dependencies
├── .gitignore
└── README.md
```

---

## Running the Project

Clone the repository and install the required packages.

```bash
pip install -r requirements.txt
```

Start the FastAPI server.

```bash
uvicorn main:app --reload --host 0.0.0.0 --port 8008
```

---

## API Endpoints

### Health Check

```http
GET /ping
```

Example response:

```json
{
  "ping": "pong!"
}
```

### Stock Forecast

```http
POST /predict
```

Example request:

```json
{
  "ticker": "MSFT"
}
```

Example response:

```json
{
  "ticker": "MSFT",
  "forecast": {
    "07/02/2026": 444.11,
    "07/03/2026": 444.10
  }
}
```

---

## What I Learned

Through this project I learned how to:

* Build REST APIs using FastAPI
* Create request and response schemas with Pydantic
* Serve a machine learning model through an API
* Validate incoming JSON requests
* Return structured JSON responses
* Organize a Python project into separate application and model layers
* Debug dependency and deployment issues while adapting an older tutorial to a modern Python environment

---

## Future Improvements

* Support forecasting for multiple stock tickers without retraining on every request
* Cache trained models
* Add automated tests
* Containerize the application with Docker
* Deploy the API to a cloud hosting platform such as Render
* Add logging and monitoring
