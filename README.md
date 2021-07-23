
<img alt="Drupal Logo" src="https://www.drupal.org/files/Wordmark_blue_RGB.png" height="60px">
<img src="https://www.terraform.io/assets/images/logo-hashicorp-3f10732f.svg" align="right" width="300">
<img src="https://docs.aws.amazon.com/assets/images/aws_logo_dark.png" align="left" width="300">














# Drupal Deployment on AWS using Terraform 


<a href="https://img.shields.io/badge/autoscaling-v4.1.0-%23c7c91c">
<img src="https://img.shields.io/badge/autoscaling-v4.1.0-%23c7c91c" /></a>

<a href="https://img.shields.io/badge/alb-v6.0.0-%238c66d9">
<img src="https://img.shields.io/badge/alb-v6.0.0-%238c66d9" /></a>


<a href="https://img.shields.io/badge/terraform--aws--rds--source-v3.0.0-ff69b4">
<img src="https://img.shields.io/badge/terraform--aws--rds--source-v3.0.0-ff69b4" /></a>
<a href="https://img.shields.io/badge/terraform--aws--rds--read-v3.0.0-ad7521">
<img src="https://img.shields.io/badge/terraform--aws--rds--read-v3.0.0-ad7521" /></a>

<a href="https://img.shields.io/badge/vpc-v3.2.0-red">
<img src="https://img.shields.io/badge/vpc-v3.2.0-red" /></a>
<a href="https://img.shields.io/badge/security__group__asg-v4.0.0-brightgreen">
<img src="https://img.shields.io/badge/security__group__asg-v4.0.0-brightgreen" /></a>
<a href="https://img.shields.io/badge/security__group__rds-v4.0.0-important">
<img src="https://img.shields.io/badge/security__group__rds-v4.0.0-important" /></a>





Drupal :- Drupal is an open source content management platform supporting a variety of
websites ranging from personal weblogs to large community-driven websites. For
more information, visit the Drupal website, [Drupal.org][Drupal.org], and join
the [Drupal community][Drupal community].

Terraform:-Terraform is a tool for building, changing, and versioning infrastructure safely and efficiently.

AWS:- Deploying Drupal on AWS makes it easy to use AWS services to further enhance the performance and extend functionality of your content management framework.

The goal of this project is to host Drupal site on AWS via Terraform  it's a cross-platform, extensible tool that codifies APIs into declarative configuration files that can be shared amongst team members, treated as code, edited, reviewed, and versioned.


# What are we trying to implement?

A virtual private cloud (VPC) that is configured across two Availability Zones. For each Availability Zone, this Quick Start provisions one public subnet and one private subnet, according to AWS best practices.

In the public subnets, Linux bastion hosts in an AWS Auto Scaling group to provide secure access to allow inbound Secure Shell (SSH) access to Amazon EC2 instances in the private subnets.

In the public subnets, managed network address translation (NAT) gateways to provide outbound internet connectivity for instances in the private subnets.

In the private subnets, a web server instance (Amazon Machine Image, or AMI) in an AWS Auto Scaling group to host the Drupal servers and Amazon Aurora database instances.

AWS Auto Scaling, which allows the Drupal cluster to add or remove servers based on use.
Integration of AWS Auto Scaling with Elastic Load Balancing, which automatically adds and removes instances from the load balancer. The default installation sets up low and high CPU-based thresholds for scaling the instance capacity up or down.

An AWS Identity and Access Management (IAM) role to enable AWS resources created through the Quick Start to access other AWS resources when required.

Out-of-box integration with load balancing and performance monitoring to be able to tune for cost/performance.




#### The different areas taken into account involves:
- 1. Application Load Balancer with Autoscaling 
- 2. MySql Database
- 3. Monitoring using Prometheus and Grafana

Also, a dedicated module named Network aims to provide desired information to implement all combinations of arguments supported by AWS and latest stable version of Terraform

## Requirements

- 1. Install Terraform
- 2. Sign up for AWS 
- 3. A valid AMI, followed by next section

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

# Terraform Modules

> A curated help menu of terraform modules used in the project.

[**Module 1**](#mod1): Autoscaling

[**Module 2**](#mod2): Application Load Balancer

[**Module 3**](#mod3): Database

[**Module 4**](#mod4): Network Configurations

<a id='mod1'></a>
## Module 1: Autoscaling


### Terraform module which creates autoscaling resources on AWS with launch template

<details>
  <summary><b>Variables</b></summary>
  
```

```
</details>

<details>
  <summary><b>Constants</b></summary>
  
```

```
</details>

<a id='mod2'></a>
## Module 2: Application Load Balancer


### Terraform module which creates Application load balancer on AWS

<details>
  <summary><b>Variables</b></summary>
  
```
   
```
</details>

<details>
  <summary><b>Constants</b></summary>
  
```

```
</details>

<details>
  <summary><b>Outputs</b></summary>
  
```

```
</details>

<a id='mod3'></a>
## Module 3: Database



### Terraform module which creates RDS resources on AWS and reads from it

<details>
  <summary><b>Variables</b></summary>
  
```
  
```
</details>

<details>
  <summary><b>Constants</b></summary>
  
```

```
</details>

<details>
  <summary><b>Outputs</b></summary>
  
```

```
</details>


<a id='mod4'></a>
## Module 4: Network Configurations


### Terraform module which create VPC, security groups for auto scaling groups and RDS on AWS

<details>
  <summary><b>Variables</b></summary>
 
  ```
 
 ```
</details>

<details>
  <summary><b>Constants</b></summary>
  
  ```
 
  ```

</details>

<details>
  <summary><b>Outputs</b></summary>
  
```
 

```
</details>



  
README.md
Displaying README.md.
