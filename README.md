# MongoDB Deployment on Kubernetes

This repository contains YAML files to deploy MongoDB on a Kubernetes cluster with a Deployment, Secrets, and Service.

## Features

- **Deployment:** Single MongoDB pod exposing port `27017` with credentials from a Secret.
- **Headless Service:** Enables pod-to-pod communication using `clusterIP: None`.
- **Secrets:** Stores base64-encoded MongoDB credentials securely.

## Files

- `mongodb-deployment.yaml`: Defines the Deployment and Service.
- `mongodb-secret.yaml`: Contains Secrets with credentials.
- `mongodb-service.yaml`: Defines the Service for MongoDB.

## Prerequisites

- Kubernetes cluster (e.g., Minikube, GKE, EKS).
- `kubectl` CLI configured.

## Usage

1. Apply Secrets:
    ```bash
    kubectl apply -f mongodb-secret.yaml
    ```
2. Deploy MongoDB:
    ```bash
    kubectl apply -f mongodb-deployment.yaml
    ```
3. Apply Service:
    ```bash
    kubectl apply -f mongodb-service.yaml
    ```
4. Verify:
    ```bash
    kubectl get pods
    ```

## Cleanup

Delete resources:
```bash
kubectl delete -f mongodb-deployment.yaml
kubectl delete -f mongodb-secret.yaml
kubectl delete -f mongodb-service.yaml
```
