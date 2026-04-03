# Terraform EC2 Instance

This Terraform configuration creates an AWS EC2 instance with a security group.

## Prerequisites

- Terraform >= 1.0
- AWS account with appropriate credentials
- AWS CLI configured or environment variables set

## Files Description

- **provider.tf** - AWS provider configuration
- **variables.tf** - Input variables with default values
- **main.tf** - EC2 instance and security group resources
- **outputs.tf** - Output values for instance information
- **terraform.tfvars** - Variable values
- **.gitignore** - Git ignore patterns

## Usage

### Initialize Terraform

```bash
tf-init
```

### Plan the deployment

```bash
tf-plan
```

### Apply the configuration

```bash
tf-apply
```

### Destroy the resources

```bash
tf-destroy
```

## Configuration

Edit `terraform.tfvars` to customize:

- `aws_region` - AWS region (default: us-east-1)
- `instance_type` - EC2 instance type (default: t2.micro)
- `instance_name` - Name tag for the instance
- `enable_monitoring` - Enable CloudWatch monitoring
- `root_volume_size` - Root volume size in GB
- `enable_public_ip` - Enable public IP assignment

## Outputs

After applying, the following outputs are available:

- `instance_id` - ID of the EC2 instance
- `instance_public_ip` - Public IP address
- `instance_private_ip` - Private IP address
- `security_group_id` - Security group ID
- `security_group_name` - Security group name
- `ssh_command` - SSH command to connect to the instance

## Security Notes

- Change SSH access CIDR from 0.0.0.0/0 to your specific IP
- Use a key pair for authentication
- Enable encryption for root volume
- Review security group rules for your use case
