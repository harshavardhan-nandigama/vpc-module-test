# 🧪 VPC Module Test

This repository is used to test and validate the **`terraform-aws-vpc`** module created for the **Roboshop project**. It provisions a sample VPC setup using the module and verifies that all components (VPC, subnets, routing, NAT, peering, etc.) work as expected.

---

vpc-module-test/
├── main.tf # Calls the VPC module
├── provider.tf # Configures the AWS provider
├── variables.tf # Declares variables for the module
├── outputs.tf # Prints outputs like VPC ID and subnet IDs
├── README.md # This documentation file

## 🔧 Terraform Commands to Run This Project

```bash
# 1️⃣ Initialize the working directory
terraform init

# 2️⃣ Preview the changes Terraform will make
terraform plan

# 3️⃣ Apply the changes to create the infrastructure
terraform apply

# 4️⃣ View the output values (like VPC ID, subnet IDs)
terraform output

# 5️⃣ Destroy the infrastructure when you're done
terraform destroy

## Module Source (From main.tf)


        module "vpc" {
        source                = "../terraform-aws-vpc"
        project               = var.project
        environment           = var.environment
        cidr_block            = var.cidr_block
        public_subnet_cidrs   = var.public_subnet_cidrs
        private_subnet_cidrs  = var.private_subnet_cidrs
        database_subnet_cidrs = var.database_subnet_cidrs
        is_peering_required   = var.is_peering_required
        }
