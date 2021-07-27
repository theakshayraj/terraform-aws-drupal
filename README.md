
<img align="left" alt="Drupal Logo" src="https://www.drupal.org/files/Wordmark_blue_RGB.png" height="60px">
<img align="right" alt="Terraform" src="https://www.terraform.io/assets/images/logo-hashicorp-3f10732f.svg"  width="300">
<p align="center"><img align="middle" width="160" height="96" alt="AWS" src="https://user-images.githubusercontent.com/42437393/126828661-63749f56-2bd4-4447-9225-f41dd737025b.png"></p>
<br>

# Drupal Deployment on AWS using Terraform 

<p align="center">
<a href="https://img.shields.io/badge/drupal-v9.2.2-009cde">
<img src="https://img.shields.io/badge/drupal-v9.2.2-009cde" /></a>
  
<a href="https://img.shields.io/badge/aws-v3.37.0-FF9900">
<img src="https://img.shields.io/badge/aws-v3.37.0-FF9900" /></a> 
  
<a href="https://img.shields.io/badge/terraform-v0.15.0-844FBA">
<img src="https://img.shields.io/badge/terraform-v0.15.0-844FBA" /></a>

</p>






<br/>

Drupal :- Drupal is an open source content management platform supporting a variety of
websites ranging from personal weblogs to large community-driven websites. 

Terraform:-Terraform is a tool for building, changing, and versioning infrastructure safely and efficiently.

AWS:- Deploying Drupal on AWS makes it easy to use AWS services to further enhance the performance and extend functionality of your content management framework.

The goal of this project is to host Drupal site on AWS via Terraform  it's a cross-platform, extensible tool that codifies APIs into declarative configuration files that can be shared amongst team members, treated as code, edited, reviewed, and versioned.


## What are we trying to implement?

A virtual private cloud (VPC) that is configured across two Availability Zones. For each Availability Zone, this Quick Start provisions one public subnet and one private subnet, according to AWS best practices.

In the public subnets, Linux bastion hosts in an AWS Auto Scaling group to provide secure access to allow inbound Secure Shell (SSH) access to Amazon EC2 instances in the private subnets.

In the public subnets, managed network address translation (NAT) gateways to provide outbound internet connectivity for instances in the private subnets.

In the private subnets, a web server instance (Amazon Machine Image, or AMI) in an AWS Auto Scaling group to host the Drupal servers and Amazon Aurora database instances.

AWS Auto Scaling, which allows the Drupal cluster to add or remove servers based on use.
Integration of AWS Auto Scaling with Elastic Load Balancing, which automatically adds and removes instances from the load balancer. The default installation sets up low and high CPU-based thresholds for scaling the instance capacity up or down.

An AWS Identity and Access Management (IAM) role to enable AWS resources created through the Quick Start to access other AWS resources when required.

Out-of-box integration with load balancing and performance monitoring to be able to tune for cost/performance.




#### The different areas taken into account involves:
-  Application Load Balancer with Autoscaling 
-  MySql Database
-  Monitoring using Prometheus and Grafana

Also, a dedicated module named Network aims to provide desired information to implement all combinations of arguments supported by AWS and latest stable version of Terraform

## Requirements

-  Install Terraform
- Sign up for AWS 
- A valid AMI, followed by next section

## AMI
If you run AWS EC2 instances in AWS, then you are probably familiar with the concept of pre-baking Amazon Machine Images (AMIs). 
That is, preloading all needed software and configuration on an EC2 instance, then creating an image of that. The resulting image
can then be used to launch new instances with all software and configuration pre-loaded. This process allows the EC2 instance to come 
online and be available quickly. It not only simplifies deployment of new instances but is especially useful when an instance is part of 
an Auto Scaling group and is responding to a spike in load. If the instance takes too long to be ready, it defeats the purpose of dynamic scaling.

## Summary of Resources
-  3 Security Groups
-  2 Running Instance in ASG
-  2 RDS(Primary & Replica) 

## PACKER WORKFLOW


Packer is a tool for building identical machine images for multiple platforms
from a single source configuration.


## 

To deploy this project run

```bash
1.packer fix:-command takes a template and finds backwards incompatible parts of it and brings it up to date so it can be used with the latest version of Packer. 
2.packer validate:-used to validate the syntax and configuration of a template. 
3.packer build-debug:-takes a template and runs all the builds within it in order to generate a set of artifacts.
4.terraform init:-used to initialize a working directory containing Terraform configuration files.
5.terraform plan:-used to creates an execution plan. 
6.terraform apply:-command executes the actions proposed in a Terraform plan.
7.terraform destroy:-command is a convenient way to destroy all remote objects managed by a particular Terraform configuration.
```

