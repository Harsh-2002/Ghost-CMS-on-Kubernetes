# Deploying Ghost CMS on Kubernetes with MySQL 8.0 as the database.

This repository contains the necessary Kubernetes configuration files to deploy the [Ghost](https://ghost.org/) content management system (CMS) on a Kubernetes cluster. Ghost is a popular, open-source blogging platform that provides a clean and minimalist interface for writing and publishing content.

This guide walks you through the step-by-step process of setting up a Ghost CMS deployment on Kubernetes, including the necessary components such as a database, persistent storage, ingress, and TLS certificates.

## Prerequisites

Before you begin, make sure you have the following prerequisites:

1. A Kubernetes cluster with the following components installed:
   - NGINX Ingress Controller
   - Cert Manager
2. `kubectl` installed and configured to access your Kubernetes cluster.
3. Git installed on your local machine.

## Getting Started

1. Clone this repository to your local machine:

   ```
   git clone https://github.com/Harsh-2002/Ghost-CMS-on-Kubernetes.git
   cd Ghost-CMS-on-Kubernetes
   ```

2. Review the configuration files in the repository & edit the configuration `env` values. 

3. Deploy the Ghost CMS and its supporting infrastructure to your Kubernetes cluster:

   ```
   kubectl apply -f ghost-deployment.yaml
   kubectl apply -f mysql-deployment.yaml
   kubectl apply -f ghost-persistent-volume.yaml
   kubectl apply -f mysql-persistent-volume.yaml
   kubectl apply -f ghost-ingress.yaml
   kubectl apply -f ghost-certificate.yaml
   ```

4. Wait for the deployments, persistent volumes, ingress, and certificate to be created and become ready.

5. Verify the deployment:

   ```
   kubectl get pods
   kubectl get svc
   kubectl get ingress
   kubectl get certificate
   ```

6. Once everything is ready, you should be able to access your Ghost CMS at the specified domain.

## Features

- **Ghost Deployment**: A Kubernetes Deployment for the Ghost CMS application.
- **MySQL (MariaDB) Deployment**: A Kubernetes Deployment for the MySQL (MariaDB) database used by Ghost.
- **Persistent Volumes**: Persistent volume claims for storing Ghost and MySQL data.
- **Ingress**: A Kubernetes Ingress resource for exposing the Ghost CMS to the internet.
- **TLS Certificates**: Automatic TLS certificate generation and management using Cert Manager.

## Contributions

Contributions to this repository are welcome. If you find any issues or have suggestions for improvements, please feel free to open an issue or submit a pull request.
