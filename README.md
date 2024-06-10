# Terraform Lightsail Project

This project demonstrates the use of Terraform to create and manage AWS Lightsail servers. The Terraform code is organized into separate folders to enhance modularity and maintainability. The project includes a shell script to set up a basic web server on the Lightsail instance.

## Project Overview

This repository contains a basic Terraform configuration to deploy an AWS Lightsail server. The project is organized into multiple folders, each containing specific Terraform code to manage different aspects of the infrastructure. A shell script is provided to install and configure a web server on the Lightsail instance.

## Features

- **Modular Terraform Code**: Terraform configurations are separated into different folders (`code1`, `code2`, `code3`, `code4`) for better organization and maintainability.
- **Automated Web Server Setup**: A `script.sh` file is used to install and start an Apache web server, and to deploy a simple HTML page indicating the server was deployed via Terraform.
- **Output Information**: Terraform outputs the public and private IP addresses of the created Lightsail server.

## Prerequisites

- **Terraform**: Install Terraform for infrastructure provisioning.
- **AWS Account**: An AWS account with appropriate permissions to create Lightsail instances.

## Getting Started

1. **Clone the repository**:
   ```bash
   git clone https://github.com/tyleboyd/Devops_Project.git
   cd Devops_Project

2. **Navigate to the Terraform code directory**:
The Terraform code is organized into code1, code2, code3, and code4 directories. Navigate to each directory to review and apply the configurations.

3. **Initialize Terraform**:
Navigate to the first code directory and initialize Terraform:
cd code1
terraform init

4. **Apply Terraform configurations**:
Apply the Terraform configurations in each code directory:
terraform apply

5. **Check Outputs**:
After applying the configurations, Terraform will output the public and private IP addresses of your Lightsail server:
output "my-public-ip" {
  value = aws_lightsail_instance.custom.public_ip_address
}

output "my-private-ip" {
  value = aws_lightsail_instance.custom.private_ip_address
}

Usage: 
Web Server Deployment: The script.sh file contains commands to install and start the Apache web server on the Lightsail instance, and to deploy a simple HTML page. This script is executed through the user data in the Terraform code.
sudo yum install -y httpd
sudo systemctl start httpd
sudo systemctl enable httpd
echo '<h1>Deployed via Terraform</h1>' | sudo tee /var/www/html/index.html

Accessing the Web Server: 
Use the public IP address provided in the Terraform output to access the web server.