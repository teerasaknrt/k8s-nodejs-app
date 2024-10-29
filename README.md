# K8s Node.js App

This is a simple Node.js application designed for deployment on a Kubernetes cluster. The app responds with "Hello from Kubernetes Node.js app!" when accessed.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Building the Docker Image](#building-the-docker-image)
- [Deploying on Kubernetes](#deploying-on-kubernetes)
- [Accessing the Application](#accessing-the-application)
- [Contributing](#contributing)
- [License](#license)

## Prerequisites

Before you begin, ensure you have the following installed on your machine:

- [Node.js](https://nodejs.org/) (v14 or later)
- [Docker](https://www.docker.com/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

## Getting Started

1. Clone the repository:

```bash
   git clone https://github.com/teerasaknrt/k8s-nodejs-app.git
   cd k8s-nodejs-app
```

2. Install the required packages:
```bash
    npm install
```

## Building the Docker Image

To build the Docker image, run the following command in the project root directory:
```bash
    docker build -t my-nodejs-app .
```

## Deploying on Kubernetes

1. Start Minikube:
```bash
    minikube start
```

2. Load the Docker image into Minikube:
```bash
    minikube image load my-nodejs-app:latest
```

3. Create the Kubernetes deployment and service:
```bash
    kubectl apply -f deployment.yaml
    kubectl apply -f service.yaml
```

4. Check the status of the deployment and pods:
```bash
    kubectl get deployments
    kubectl get pods
```

5. Check the status of the service:
```bash
    kubectl get services
```

## Accessing the Application

To access the application, run the following command to open the service in your web browser:
```bash
    minikube service nodejs-app-service
```

You should see the message "Hello from Kubernetes Node.js app!" in your browser.