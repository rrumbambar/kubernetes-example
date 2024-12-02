# Example of Kubernetes Deployment for UI and Database

This project deploys a web application (UI) and its accompanying database (Grafana+Prometheus) onto a Kubernetes cluster. The deployment was converted from a Docker Compose setup.

---

## Prerequisites

Before deploying this project, ensure the following are installed:

1. **Kubernetes Cluster**: Minikube, Docker Desktop
2. **kubectl**: Kubernetes command-line tool.

---

## Components

This project includes the following Kubernetes objects:

1. **Deployments & Services**:
   - `grafana.yaml`: Manages the UI service pod and exposes the UI application.
   - `prometheus.yaml`: Manages the database pod and provides access to the database.
2. **Persistent Volumes Claim**:
   - `prom-data-pvc.yaml`: Ensures data persistence for the database.
3. **Secret**:
   - `grafana-secret.yaml`: Stores credentials for UI application.
4. **Config Maps**:
   - `grafana-config.yaml`: Contains configuration file for Grafana.
   - `prometheus-config.yaml`: Contains configuration file for Prometheus.

---

## Setup Instructions

1. Start your minikube cluster `minikube start`.
2. Navigate to directory with kubernetes configuration files `cd grafana-prometheus`.
3. Deploy the application `kubectl apply -f .`.
4. Verify pods and services `kubectl get pods`, `kubectl get svc`.
5. For detailed logs `kubectl logs <pod-name>`.

---

## Acessing the application

1. Get the external IP/URL for services: `minikube service prometheus-service`, `minikube service grafana-service`.
2. Open the provided URLs in your browser to access the UI.

---

## Cleanup

1. Remove all deployed resources `kubectl delete -f .`.
2. Stop minikube `minikube stop`.







