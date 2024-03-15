# Deploy to Backend to Prod Env

![GitHub Workflow Status](https://img.shields.io/github/workflow/status/Devops0091/ec2-code-deploy-direct/Deploy%20to%20Backend%20to%20Prod%20Env?label=Workflow%20Status&style=flat-square)

Automated GitHub Action workflow for deploying an application to an EC2 instance directly using SSH. This workflow automates the deployment process to your EC2 instance running Ubuntu.

## Overview

This GitHub Action workflow automates the deployment process of your application to an EC2 instance. It assumes that you have already set up your EC2 instance, SSH key pair, and GitHub Secrets. The workflow installs necessary tools, such as Git, AWS CLI, and OpenSSH Client, and then proceeds with deploying your application.

## Prerequisites

Before running this workflow, ensure that you have set up the following environment variables as GitHub Secrets in your repository settings:

- `AWS_ACCESS_KEY_ID`: Your AWS access key ID.
- `AWS_SECRET_ACCESS_KEY`: Your AWS secret access key.
- `SSH_PRIVATE_KEY`: Your SSH private key used for authentication with the EC2 instance.
- `SSH_HOST`: The hostname or IP address of your EC2 instance.

## Workflow Steps

1. **Install Git, AWS CLI, and OpenSSH Client**: Installs necessary tools required for the deployment process.
2. **Add public IP to AWS security group for Web App**: Adds the public IP of the GitHub Actions runner to the AWS security group associated with your EC2 instance.
3. **Configure SSH for Web App deployment**: Configures SSH with the provided private key for authentication.
4. **Deploy code to Web App**: SSH into the EC2 instance and pull the latest code from the repository.
5. **Make Scripts Executable**: SSH into the EC2 instance and make scripts executable after deployment.

## Usage

To use this workflow in your repository:

1. Copy the contents of `.github/workflows/deploy.yml` into your repository's workflows directory.
2. Ensure that you have set up the required GitHub Secrets mentioned in the prerequisites section.
3. Customize the workflow as needed for your specific deployment process.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

