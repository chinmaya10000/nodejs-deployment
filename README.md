# Node.js CI/CD Pipeline with GitHub Actions, Terraform, and Ansible

This project demonstrates setting up a CI/CD pipeline for a Node.js service using GitHub Actions. The pipeline includes provisioning an EC2 instance using Terraform, configuring the server with Ansible, and deploying the application.

## Table of Contents

- [Project Description](#project-description)
- [Prerequisites](#prerequisites)
- [Setup](#setup)
  - [Provision EC2 Instance with Terraform](#provision-ec2-instance-with-terraform)
  - [Configure Server with Ansible](#configure-server-with-ansible)
- [Usage](#usage)
- [CI/CD with GitHub Actions](#cicd-with-github-actions)
- [Secrets Management](#secrets-management)
- [License](#license)

## Project Description

This project sets up a CI/CD pipeline for deploying a simple Node.js service. The service includes a single route (`/`) that returns "Hello, world!". The deployment process involves:

1. Provisioning an EC2 instance with Terraform.
2. Configuring the server with Ansible to install Node.js and deploy the application.
3. Automating the deployment using GitHub Actions.

## Prerequisites

Before you begin, ensure you have the following:

- An AWS account for provisioning EC2 instances.
- Terraform installed on your local machine.
- Ansible installed on your local machine.
- A GitHub repository for your Node.js service.
- An SSH key pair for accessing the EC2 instance (`eks-iac-key.pem`).

## Setup

### Provision EC2 Instance with Terraform

1. Create a `main.tf` file to define the infrastructure for an EC2 instance.
2. Initialize Terraform and apply the configuration to provision the EC2 instance.

### Configure Server with Ansible

1. Create an Ansible playbook (`node_service.yml`) to configure the server, install Node.js, and deploy your Node.js application.
2. Run the Ansible playbook manually to verify the server configuration and application deployment.

## Usage

- Access the Node.js service at `http://<ec2-instance-ip>:80`.

## CI/CD with GitHub Actions

1. Create a GitHub Actions workflow file (`.github/workflows/deploy.yml`) to automate the deployment process.
2. The workflow should include steps to:
   - Checkout the code.
   - Set up Node.js.
   - Install Ansible.
   - Run the Ansible playbook to deploy the application.

## Secrets Management

Add the following secrets to your GitHub repository:

- `EC2_PUBLIC_IP`: The public IP address of your EC2 instance.
- `SSH_PRIVATE_KEY`: The private SSH key to access your EC2 instance.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.