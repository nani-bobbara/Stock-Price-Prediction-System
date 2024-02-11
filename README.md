# Stock Price Prediction System

This repository contains the architecture and components for a stock price prediction system. The system collects live data from the S&P index, preprocesses it, trains an AI model, and provides real-time predictions through a user-friendly web interface.

## Components

1. **Collector Service**
    - Collects live data from the S&P index using free sources (e.g., FRED, WSJ, Google Finance).
    - Publishes data to RabbitMQ for further processing.

2. **Feeder Service**
    - Subscribes to collected data from RabbitMQ.
    - Performs data cleaning, transformation, and filtering.
    - Publishes cleaned data to another RabbitMQ queue.

3. **Trainer Service**
    - Subscribes to cleaned data from RabbitMQ.
    - Trains an AI model (e.g., LSTM, ARIMA) using Azure Databricks.
    - Evaluates model performance and fine-tunes hyperparameters.

4. **Predictor Service**
    - Subscribes to prediction requests from the UI App.
    - Uses the trained AI model to generate real-time stock price predictions.
    - Deploys the model as an API endpoint.

5. **UI App**
    - Provides a user-friendly web interface for interacting with the system.
    - Displays real-time S&P index data and predictions.
    - Hosted on Azure App Services.

## Technical Choices

- **Language/Frameworks**:
    - Microservices: C# and ASP.NET Worker Services
    - Data Preprocessing: Pandas.NET
    - Model Training: ML.NET or TensorFlow.NET
- **DAPR SDKs**:
    - Use DAPR SDKs (C#) for microservices communication.
- **Azure Services**:
    - Deploy microservices to Azure Kubernetes Service (AKS).
    - Use Azure Event Hubs for message brokering.
    - Deploy UI App on Azure App Services.
    - Store secrets in Azure Key Vault.
- **Observability and Monitoring**:
    - Implement structured logging (e.g., Serilog).
    - Use Prometheus for metrics.
    - Set up alerts for critical events.
- **CI/CD and Containers**:
    - Set up CI/CD pipelines (e.g., Azure DevOps, GitHub Actions).
    - Containerize each microservice using Docker.
    - Push images to an Azure Container Registry.

## Security and Authentication

- Secure API endpoints using JWT authentication or other methods.
- Store secrets (e.g., API keys) securely (e.g., Azure Key Vault).

## Deployment and Scaling

- Deploy microservices to Azure Kubernetes Service (AKS).
- Monitor resource utilization and scale services dynamically based on demand.

## Testing and Documentation

- Write unit tests for each microservice.
- Document architecture, deployment steps, and troubleshooting.

# Getting Started
    # 1. Clone this repository.
    # 2. Set up your Azure resources (e.g., RabbitMQ, Azure Databricks, Azure App Services).
    # 3. Deploy the Docker containers with Dapr sidecars.
    # 4. Access the UI App to explore stock price predictions.
# Contributors
     # 1.Nani 
