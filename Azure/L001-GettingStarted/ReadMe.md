#Getting Started
* This document will help you set up terraform and create a resource group in azure using terraform
* There is no attempt made to introduce the advantages of Terraform. It's assumed that this is known.

## Objective
* Create a resource group using terraform

## Prerequisities
* Windows 10 (or linux) machine with docker installed
* Azure subscription

## Overview of the steps
* Terraform has to login to azure to create resources
* One of the way for Terraform to login to azure is as a service principle
* Service principle is a application that can create/modify/delete resources in azure
* So in this excercise, we will create a service principle application and login to azure as the service principle using Terraform

## Steps involved

### Run the Azure Terraform VM
* Run the below command to run Terraform Azure VM locally
`docker container run -it --rm --mount <C:\YourWorkingDir>:/workspace zenika/terraform-azure-cli:latest`
* Remember to replace your working directory in the above command
* After running the command, you will have a terminal to the linux machine running as docker

### Login as user in to azure using azure cli
* In docker, login to azure using the below command
`az login`
* Please follow the login steps
* Once you login, your subscription id will be listed. Please make a note of it for the next step

### Create a service principle in azure
* Run the below command to create a service principle
`az ad sp create-for-rbac --role="Contributor" --scopes="/subscriptions/<subscription_id>"`
* Please note the appid (client id), password (client secret), tenant id being displayed

### Log out of Azure
* Log out of azure by running the command `az logout`

### Set environment variables for terraform to login as service principle
Run the below commands to set the environment variables for service principle login for Terraform
```
export ARM_CLIENT_ID="<0000000000000000000000000000000000000>"
export ARM_CLIENT_SECRET="<0000000000000000000000000000000000000>"
export ARM_SUBSCRIPTION_ID="<0000000000000000000000000000000000000>"
export ARM_TENANT_ID="<0000000000000000000000000000000000000>"
```

### Write the needed IAC
* create a folder in the current directory named "Lesson0001"
* Inside the folder create a file called resourcegroup.tf with the below content
```
provider "azurerm" {
  version = "~>2.0"
  features {}
}

resource "azurerm_resource_group" "rg" {
  name = "<your_resource_group_name>"
  location = "<your_resource_group_location>"
}

```

### initialize terraform
* Go in the folder by the command `cd Lesson0001`
* Run the command `terraform init`

### Create a plan
* Create a plan by running the command `terraform plan -out resourcegroup.tfplan`

### Create a destruction plan
* Create a destruction plan by running the command `terraform plan -destroy -out resourcegroup.destroy.tfplan`

### Apply plan
* Apply the plan by the command `terraform apply resourcegroup.tfplan`
* At this point, the resource group should be created in Azure

### Apply destruction plan
* The resource group could be destroyed by the command `terraform apply resourcegroup.destroy.tfplan`
* The resource group was not removed in Azure, need to investigate

Reference:
https://docs.microsoft.com/en-us/azure/developer/terraform/get-started-cloud-shell
https://learn.hashicorp.com/collections/terraform/azure-get-started?utm_source=terraform_io_download
https://hub.docker.com/r/zenika/terraform-azure-cli






