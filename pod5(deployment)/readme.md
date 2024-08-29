# NGINX Kubernetes Deployment and Service

This repository contains a simple Kubernetes setup for deploying an NGINX web server using a `Deployment` and exposing it via a `Service`. The deployment is configured with two replicas, ensuring high availability. The service uses `NodePort` to expose the application on a port that can be accessed externally.

## Prerequisites

Before running the deployment, ensure you have the following installed:

- **Kubernetes Cluster** (Minikube, Docker Desktop, or a cloud provider like AWS EKS, GCP GKE, etc.)
- **kubectl**: Kubernetes command-line tool
- **A working Docker installation** (for building your own images, if needed)

## Setup

1. **Clone this repository**:

    ```bash
    git clone <repository_url>
    cd <repository_directory>
    ```

2. **Apply the Deployment and Service YAML files**:

    ```bash
    kubectl apply -f deployment.yaml
    ```

3. **Verify the Deployment and Service**:

    After applying the manifest files, verify that the deployment and service are running correctly:

    ```bash
    # Check the status of the deployment
    kubectl get deployments
    
    # Check the status of the pods
    kubectl get pods

    # Check the service to retrieve the exposed NodePort
    kubectl get services
    ```

4. **Accessing NGINX**:

    - Once the service is up and running, the NGINX server can be accessed via the `NodePort` exposed on the cluster nodes. Find the external IP address of one of your cluster nodes and the `NodePort` assigned to the service, then access it in your browser.

    Example:

    ```bash
    # Get the NodePort assigned
    kubectl get service deployment-service
    ```

    If the `NodePort` is `30001`, and the node IP is `192.168.99.100`, access it at `http://192.168.99.100:30001`.

## Manifest Details

### Deployment

The `Deployment` resource ensures that two replicas of the NGINX container are always running. It manages updates to the pods and ensures high availability of the application.

- **Image**: `nginx` (official NGINX image from Docker Hub)
- **Replicas**: 2
- **Container Port**: 80 (default HTTP port)

### Service

The `Service` resource exposes the NGINX deployment using the `NodePort` type, which opens a specific port on all cluster nodes and redirects traffic to the deployment.

- **Type**: `NodePort`
- **Port**: 80 (mapped to the container's port 80)
- **Protocol**: TCP

## Clean Up

To delete the deployment and service, run:

```bash
kubectl delete -f deployment.yaml
