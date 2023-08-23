<img src="https://kubernetes.io/images/nav_logo2.svg" width="210" style="margin-right: 10px;">
# Kubernetes and Cluster setup on Ubuntu 20.04 and CentOS 8

## Overview
This repository contains instructions and scripts for setting up Kubernetes and creating a cluster on Ubuntu 20.04 and CentOS 8. These instructions will guide you through the process step-by-step, making it easy for you to deploy and manage containerized applications.

## Prerequisites
Before proceeding with the installation, ensure that you have the following prerequisites:
- A minimum of three virtual or physical machines running either Ubuntu 20.04 or CentOS 8.
- Each machine should have a minimum of 2 CPU cores and 2GB of RAM.
- All machines should be connected on the same network and have network connectivity.
- Basic knowledge of the Linux command line interface (CLI).

## Installation
Follow the instructions below to install Kubernetes and set up a cluster for your environment.

### Ubuntu 20.04
1. Clone or download this repository to your local machine.
2. Navigate to the `ubuntu-20.04` directory in the repository.
3. Open the `kubernetes_setup.sh` file and review the configuration options.
4. Execute the script by running `sudo ./kubernetes_setup.sh`.
5. Follow any on-screen prompts to complete the installation.
6. To create a cluster, please see the `cluster_setup.md` file in the repository.

### CentOS 8
To set up a Kubernetes cluster on CentOS 7, adhere to the following guidelines.
This comprehensive documentation will walk you through the process of configuring a cluster with a single master node and one worker node.

1. prerequisites
2. Across both K8smaster and K8sworker:
3. firewall settings
4. swap service setting
5. SELinux Setting
6. adjustments to sysctl settings
7. Install & Deploy Docker engine
8. Setting up a Kubernetes environment
9. Join the cluster
10. Verifying the cluster

## Cluster Setup
Follow the instructions in the `cluster_setup.md` file to create a Kubernetes cluster after completing the installation steps. This will guide you through the process of configuring your cluster and setting up the necessary components.

## Troubleshooting
If you encounter any issues during the installation or cluster setup process, please refer to the `troubleshooting.md` file in the repository. This document provides common troubleshooting steps and solutions for common problems.

## Contributing
Contributions are welcome! If you find any bugs or have any suggestions for improvements, please submit an issue or a pull request.

## License
This project is licensed under the [MIT License](https://github.com/your/repository/license.md). Please review the license file for more information.

## Acknowledgements
- Thank you to the Kubernetes and Linux communities for their invaluable contributions.
- Special thanks to the authors of any scripts or code used in this project.
- Refer to the `acknowledgements.md` file for a comprehensive list of references and resources.

Feel free to modify this README file to suit your specific requirements and provide additional information about your project. Good luck with your Kubernetes and cluster setup!
