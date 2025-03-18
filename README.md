# AWS CloudFormation Template for CI/CD Pipeline

## Overview
This CloudFormation template provisions a **CI/CD pipeline** using AWS CodePipeline, CodeBuild, and CodeDeploy. It also sets up **network infrastructure (VPC, subnets, security groups)** and deploys an EC2 instance for application hosting.

## Features
- **VPC Setup**: Creates a secure VPC with public subnets.
- **IAM Security**: Defines policies for CodePipeline, CodeBuild, and CodeDeploy.
- **S3 Artifact Storage**: Ensures encrypted storage of pipeline artifacts.
- **Automated Deployments**: Uses AWS CodeDeploy for zero-downtime releases.
- **EC2 Instance Deployment**: Launches an Amazon Linux 2 instance.

## Requirements
- AWS account with permissions to create resources.
- AWS CLI configured with necessary credentials.
- CloudFormation stack deployment access.

## Parameters
| Parameter Name       | Description                                      |
|----------------------|--------------------------------------------------|
| `CodePipelineName`   | Name of the pipeline                            |
| `AmiId`             | AMI ID for the EC2 instance                      |
| `VpcCidr`           | CIDR block for the VPC (default: `10.0.0.0/16`)  |
| `InstanceType`      | EC2 instance type (default: `t2.micro`)         |

## Deployment Instructions
1. **Upload the YAML file to AWS CloudFormation**
2. **Launch the stack with parameters**
3. **Monitor stack creation**
4. **Verify the pipeline in AWS CodePipeline**

## Outputs
| Output Name             | Description                                 |
|-------------------------|---------------------------------------------|
| `EC2InstanceId`         | Deployed EC2 instance ID                    |
| `EC2InstancePublicDNS`  | Public DNS name for the instance            |

## Security Considerations
- IAM roles follow the **principle of least privilege**.
- All S3 artifacts are **encrypted at rest**.
- EC2 security group allows only HTTP/HTTPS traffic.

## Future Enhancements
- Add **CloudWatch monitoring** for the pipeline.
- Enable **auto-scaling** for high availability.
- Use **AWS Secrets Manager** to manage credentials securely.

