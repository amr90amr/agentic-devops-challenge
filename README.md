# AWS VPC Infrastructure Automation with Terraform & GitHub Actions

This project demonstrates an automated Infrastructure-as-Code (IaC) pipeline using Terraform and GitHub Actions to provision and manage secure cloud resources on AWS.

## Architecture Overview
- **Cloud Provider:** AWS (`us-east-1` region)
- **Networking Components:**
  - Custom Virtual Private Cloud (VPC) with a defined CIDR block.
  - Public Subnet configured for resource placement.
  - Internet Gateway (IGW) attached to the VPC for external internet connectivity.
  - Route Tables ensuring proper traffic routing.

## CI/CD Pipeline (`.github/workflows/deploy.yml`)
The automated workflow is triggered on pushes to the main branch and performs:
1. **Checkout Code:** Retrieves the repository contents on the runner.
2. **Setup Terraform:** Installs and configures the specified Terraform version.
3. **AWS Authentication:** Securely authenticates using GitHub encrypted secrets (`AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`).
4. **Terraform Apply:** Automatically initializes and applies the infrastructure configuration with zero manual intervention.

## Verification
- GitHub Actions workflow completes with a successful `green` status.
- VPC (`challenge-vpc`) and associated subnets are successfully provisioned and verified in the AWS VPC Console.
