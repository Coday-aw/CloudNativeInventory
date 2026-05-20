# CloudNativeInventory
A modern, containerized .NET 9 inventory API built for cloud deployment, secure secret management, and automated CI/CD.
The project follows DevOps best practices and is designed for scalable, cloud‑native hosting on Azure.

## Features
- Containerized .NET 9 API using Docker
- Automated CI/CD with GitHub Actions
- Secure secrets via Azure Key Vault
- Cloud‑ready architecture aligned with Azure Container Apps
- ACR‑based image storage and automated deployments
- CI/CD Pipeline

## Architecture Summary
The system uses:
- .NET 9
- Docker
- Azure Container Registry
- GitHub Actions
- Azure Key Vault
- Azure Container Apps

## Local Development

### Run locally

- dotnet restore
- dotnet build
- dotnet run --project CloudNativeInventory.Api

### Run with Docker
- docker build -t cloudnativeinventory .
- docker run -p 8080:8080 cloudnativeinventory

## Deployment
Deployment is fully automated:
- Build & test
- Build Docker image
- Deploy to Azure

Trigger by pushing to main or running the workflow manually.

## Security
- Secrets stored in Azure Key Vault
- Managed identities for secure access
- No secrets in code or config files

