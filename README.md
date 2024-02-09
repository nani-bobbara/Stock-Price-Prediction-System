# Stock-Price-Prediction-System

This repository contains the architecture and components for a stock price prediction system. The system is designed to collect live data from the S&P index, preprocess it, train an AI model, and provide real-time predictions through a user-friendly web interface.

# Components

    # 1. Collector
          Collects live data from the S&P index using free sources (e.g., FRED, WSJ, Google Finance).
          Publishes data to RabbitMQ for further processing.
    # 2. Feeder
          Subscribes to collected data from RabbitMQ.
          Performs data cleaning, transformation, and filtering.
          Publishes cleaned data to another RabbitMQ queue.
    # 3. Trainer
          Subscribes to cleaned data from RabbitMQ.
          Trains an AI model (e.g., LSTM, ARIMA) using Azure Databricks.
          Evaluates model performance and fine-tunes hyperparameters.
    # 4. Predictor
          Subscribes to predictions requests from the UI App.
          Uses the trained AI model to generate real-time stock price predictions.
          Deploys the model as an API endpoint.
    # 5. UI App
          Provides a user-friendly web interface for interacting with the system.
          Displays real-time S&P index data and predictions.
          Hosted on Azure App Services.

# Communication Channels
    Dapr sidecars handle communication between containers using gRPC/HTTP protocols.
    RabbitMQ serves as the message broker for asynchronous communication.
    Azure AI model provides predictions.
    Azure Application Insights captures telemetry data for observability.

# Getting Started
    # 1. Clone this repository.
    # 2. Set up your Azure resources (e.g., RabbitMQ, Azure Databricks, Azure App Services).
    # 3. Deploy the Docker containers with Dapr sidecars.
    # 4. Access the UI App to explore stock price predictions.
# Contributors
     # 1.Nani 
