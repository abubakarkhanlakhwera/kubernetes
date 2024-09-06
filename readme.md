# Kubernetes Setup and Deployment

This repository contains scripts and configuration files for setting up and managing a Kubernetes cluster. It is designed for students, developers, and DevOps enthusiasts looking to practice Kubernetes on local and cloud environments.

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Cluster Management](#cluster-management)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This project includes bash scripts and Kubernetes manifests that allow users to quickly set up a Kubernetes cluster, manage nodes, and deploy applications. The scripts are tailored for local environments, but they can be adapted for cloud providers like AWS.

## Prerequisites

To use this repository, you'll need the following:

- Ubuntu (or any Linux-based system)
- Docker
- Kubernetes CLI (kubectl)
- VMware (for local Kubernetes setups)
- AWS Account (optional for cloud deployment)
- Bash scripting knowledge (to customize and run the scripts)

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/abubakarkhanlakhwera/kubernetes.git
    cd kubernetes
    ```

2. Install Docker and Kubernetes:
    - You can follow the official Docker and Kubernetes installation guides.
    - For local Kubernetes, you can use VMware to set up VMs and deploy a cluster.

3. Run the setup scripts:
    ```bash
    ./scripts/setup_kubernetes.sh
    ```

    This script will set up your local Kubernetes cluster with all necessary configurations.

## Cluster Management

This repository includes a set of scripts for cluster management:

- `reset_cluster.sh`: Resets the Kubernetes cluster by stopping services, killing processes, and cleaning up data directories.
- `start_cluster.sh`: Starts the Kubernetes services and initializes the cluster.
- `stop_cluster.sh`: Stops all Kubernetes services and processes.

## Usage

- **Deploy Applications**: Use the included Kubernetes manifests to deploy containerized applications.
- **Manage Pods and Services**: Use `kubectl` commands to manage your pods, services, and other Kubernetes resources.
- **Monitor Cluster**: Monitor your cluster health and performance using built-in Kubernetes tools or third-party solutions like Prometheus and Grafana.

## Contributing

Contributions are welcome! Please fork this repository and submit a pull request with any improvements or bug fixes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
