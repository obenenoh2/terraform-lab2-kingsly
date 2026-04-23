# Terraform Lab 2 - VPC with Public Subnet

## Overview
This Terraform project creates a complete AWS VPC infrastructure with public subnet, internet gateway, and routing configuration in Frankfurt (eu-central-1) region.

## Resources Created

### Networking
- **VPC**: 10.20.0.0/16 with DNS hostnames enabled
- **Internet Gateway**: Attached to VPC for internet access
- **Public Subnet**: 10.20.1.0/24 in eu-central-1a
- **Route Table**: Default route (0.0.0.0/0) pointing to Internet Gateway
- **Route Table Association**: Links public subnet to route table

## Architecture

eu-central-1 (Frankfurt)
│
└── VPC: 10.20.0.0/16
├── Internet Gateway (attached)
├── Route Table (public)
│ └── 0.0.0.0/0 → Internet Gateway
└── Public Subnet: 10.20.1.0/24 (eu-central-1a)
└── Auto-assign public IP: enabled


## Prerequisites

- Terraform >= 1.5.0
- AWS CLI configured with appropriate credentials
- AWS account with permissions to create VPC resources

## Usage

### Clone the repository
```bash
git clone https://github.com/obenenoh2/terraform-lab2-kingsly.git
cd terraform-lab2-kingsly

Initialize Terraform
terraform init

Plan the infrastructure
terraform plan

Apply the configuration
terraform apply

Outputs
No outputs configured for this lab (will be added in Lab 3).

State Management
State file is stored locally (not in git - see .gitignore)

Remote state will be configured in later labs

Tags
All resources are tagged with:

Lab = "02"

ManagedBy = "terraform"

Next Steps
Lab 3 will extend this infrastructure by adding:

Security group with web access (SSH, HTTP, HTTPS)

EC2 instance (t2.micro) with user data to install web server

Public IP assignment

Notes
This infrastructure is designed for learning purposes

Keep resources running for Lab 3 (EC2 deployment)

Resources are mostly free (no hourly charges for VPC components)

Author
Oben Enoh

License
This project is for educational purposes.
