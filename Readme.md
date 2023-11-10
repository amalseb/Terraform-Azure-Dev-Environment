# Dev Environment Setup with Terraform

This project automates the creation of a development environment in Microsoft Azure using Terraform. It provisions the necessary resources, including a virtual machine, a virtual network, and a network security group, to set up a secure and isolated development environment.

## Prerequisites

Before you begin, ensure you have the following prerequisites installed on your machine:

- [Terraform](https://www.terraform.io/downloads.html) (>= 0.12)
- [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli)
- SSH key pair (required for SSH access to the virtual machine)

## Getting Started

### Azure Authentication

Sign in to your Azure account using the Azure CLI:

```bash
az login
```

### Configuration

Customize the configuration by modifying the `terraform.tfvars` file if needed.

### Initialize Terraform and Apply

Initialize Terraform and apply the configuration:

```bash
terraform init
terraform apply
```

## Configuration

- `main.tf`: Defines the Terraform configuration, including the Azure provider and the resources to be provisioned.
- `terraform.tfvars`: Contains variables and their values. Customize these variables to match your requirements.
- `variables.tf`: Defines Terraform input variables, including the `host_os` variable.
- `customdata.tpl`: The template file used for custom data when provisioning the virtual machine.

## Outputs

- `public_ip_address`: Displays the public IP address of the created virtual machine.

### SSH Configuration

After provisioning, you can SSH into the virtual machine using the following command:

```bash
ssh -i ~/.ssh/id_rsa adminuser@<public_ip_address>
```

Replace `<public_ip_address>` with the actual public IP address displayed in the Terraform outputs.

### Cleanup

To destroy the resources and clean up the environment, run:

```bash
terraform destroy
```

Follow the prompts to confirm the destruction.

## Acknowledgments

- [Terraform](https://www.terraform.io/)
- [Microsoft Azure](https://azure.microsoft.com/)

