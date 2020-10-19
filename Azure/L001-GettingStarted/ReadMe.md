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

### Login as user in to azure using azure cli

### Create a service principle in azure

### Get the credential details of the created service principle created

### Set environment variables for terraform to login as service principle

### initialize terraform

### Create a plan

### Create a destruction plan

### Apply plan

### Apply destruction plan

Reference:
https://docs.microsoft.com/en-us/azure/developer/terraform/create-linux-virtual-machine-with-infrastructure
https://learn.hashicorp.com/collections/terraform/azure-get-started?utm_source=terraform_io_download
https://hub.docker.com/r/zenika/terraform-azure-cli


Next in Line
https://docs.microsoft.com/en-us/azure/developer/terraform/create-linux-virtual-machine-with-infrastructure





