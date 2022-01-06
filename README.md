# CSYE 6225 assignment 8

# Author: Yingyi Chen

# Create AMI in AWS using Packer locally or using github actions to build automatically
1. build locally: enter access key, secret key, and subnet id
2. build in github actions: setup secrets in github

## Install Hashicorp-Packer
https://learn.hashicorp.com/tutorials/packer/get-started-install-cli

## Files
There should be ami.json and vars.json file.
vars.json should be like:
{
    "type" : "amazon-ebs",
    "aws_region": "us-east-",
    "aws_access_key": "your access key",
    "aws_secret_key":"your secret key",
    "subnet_id":"subnet id",
    "source_ami": "ami-id",
    "instance_type": "t2.micro",
    "ssh_username": "ubuntu",
    "ami_name": "",
    "ami_description":"",
    "prod_account_id":"shared account"
    }

## Steps to create an AMI
> validate files
` packer validate -var-file="vars.json" ami.json`
  
> build images
` packer build -var-file="vars.json" ami.json` 


