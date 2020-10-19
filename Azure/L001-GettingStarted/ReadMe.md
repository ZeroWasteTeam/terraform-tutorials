#Getting Started

## Prerequisities
* Why use Terraform with azure is not covered here.
* Given the you have decided to use terraform, the below steps help you create a resources in azure using terraform
* Its expected that you have docker installed in your machine
* You have a azure subscription


## Objective
* Create a resource group using terraform

## Theory
* Terraform has to login to azure to create resources
* It's recommened that terraform logins as service principle to create resources
* Service principle is a application that can create/modify/delete resources in azure

## Steps involved

### Login as user in to azure using azure cli

### Create a service principle in azure

### Get the credential details of the created service principle created

### Set environment variables for terraform to login as service principle

### initialize terraform

### Create a plan

### Create a destruction plan

### Apply plan

### Apply destruction plan


https://docs.microsoft.com/en-us/azure/developer/terraform/create-linux-virtual-machine-with-infrastructure
https://learn.hashicorp.com/collections/terraform/azure-get-started?utm_source=terraform_io_download
https://hub.docker.com/r/zenika/terraform-azure-cli


Next in Line
https://docs.microsoft.com/en-us/azure/developer/terraform/create-linux-virtual-machine-with-infrastructure





