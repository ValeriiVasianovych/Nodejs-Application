# Argo Events and Argo Workflows Example App

This repository demonstrates how to use Argo Events and Argo Workflows together in a Kubernetes environment. The example app is a simple Node.js application that will be used to illustrate how Argo Events can trigger workflows based on changes in a GitHub repository. 

## Overview

1. **Argo Events** will listen for changes in the GitHub repository.
2. **Argo Sensors** will respond to these changes by triggering a **Argo Workflow**.
3. The **Argo Workflow** will execute the following steps:
   - Clone the repository.
   - Build a Docker image and push it to Docker Hub.
   - Deploy the Docker image to a new Kubernetes Deployment.

## Prerequisites

- Kubernetes cluster
- Argo Workflows installed on the Kubernetes cluster
- Argo Events installed on the Kubernetes cluster
- Access to Docker Hub
- A GitHub repository with this example app
- Sealead Secrets in Kubernetes for GitHub token and Docker Hub credentials
- Argo CD for deploying the Argo Events and Argo Workflows configurations

## Repository Setup

1. **Push to GitHub Repository:**
   - Ensure your Node.js app is pushed to a GitHub repository. The example app will be cloned by the workflow.

2. **Argo Events Configuration:**
   - Argo Events will monitor changes in the GitHub repository and trigger a sensor to start the workflow.

3. **Argo Workflows Configuration:**
   - The workflow is defined to clone the repository, build and push the Docker image, and deploy it to Kubernetes.

## Getting Started

1. Apply the Argo Events, Sensor, and Workflow configurations to your Kubernetes cluster.
2. Push changes to your GitHub repository.
3. Argo Events will detect the push event, trigger the Sensor, which in turn will execute the Workflow.
4. Monitor the workflow execution through the Argo UI.

## Conclusion

This example demonstrates how to integrate Argo Events and Argo Workflows to automate CI/CD tasks in Kubernetes. Adjust the configurations according to your specific requirements and environment.

For more details on Argo Workflows and Argo Events, refer to the [Argo Documentation](https://argoproj.github.io/argo/).