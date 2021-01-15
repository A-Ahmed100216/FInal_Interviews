# AWS

## What is Cloud Computing?
* On-demand delivery of compute resources, storage, networking, database etc via the internet with a pay-as-you-go pricing model

## Service Models
* Infrastructure as a Service - highest level of control over resources e.g. AWS
* Platform as a Service - doesn't need management of infrastructure
* Software as a Service - end user applications, maintenance or management not required e.g. gmail

# Cloud vs On-premise
On-premise
* Physical infrastructure, locally installed on company own servers.
* Capital expenses  
* Scaling up is expensive and time consuming, scaling down does not reduce fixed costs

Cloud
* Purchased from AWS or other cloud providers who are responsible for maintaining facilities and hardware.
* Easy to scale
* Costs based on usage

# Advantage of Cloud
1. Trade capital expense for variable expense
2. Massive economies of scale
3. Stop guessing capacity
4. Increase speed and agility
5. Stop spending money on running and maintaining data centres
6. Go global in minutes

## AWS Services
1. Compute - Amazon EC2, ECS,  

# AWS Global Infrastrutcure
* Regions - Distinct geogrpahical area isolated from others to ahcive fault tolerance and stability. Contains 2 or more Availability Zones
* AZs - Fully isolated partition of the AWS Global Infrastructure. Consist of discrete data centres. Designed for fault isolation. Interconnected with other AZs via high speed private networking
* Data Centres - where data resides and data processing occurs. Designed for security  


## What is a network
* 2 or more machine connected together via a router or switch.
* Can be logicaly partitioned into subnets
## What is OSI MOdel
* Used to understand how communications takes place in the cloud and basic netwroking,
* 7 layers (application[7], presentation, session, transport, network, data link, physical[1]).

# What is a VPC?
* Virtual Private Cloud
* Amazon allows you to provision a logcally isolated section of the AWS cloud where you can luanch AWS resources in a virtual network.
* Allows you to define networking resources such as ip addresses, subnets, route tables, gateways.
* Belong to a single AWS region
* Largest ip block is /16

## What is a route table?
* Set of rules you can configure to direct network traffic from a subnet.
* Each route specifies a target and destination
* By default, every route contains a local route to enable communication with vpc

## What is an Internet Gateway?
* Allows communication between instances in your vpc and the internet.
* Provide a target in your vpc route tables for internet traffic
* perform network address translation for instances that were assigned public ip addresses.

# Security Grousp
* Act at the instance level
* Act as virtual firewalls that control inbound and outbound traffic to and form your instance.
* Allow only rules
* Stateful - return traffic automatically allowed

# Network Access Control Lists
* 2nd firewall option
* Control traffic in and out of the subnet
* Can set up rules for allow or deny
* Stateless - inbound and outbound rules must be defined - return traffic must be explicitly allowed.

# Amazon Route 53
* Highly available and scalable DNS web service
* DNS - Domain name system - translates web addresses into ip addresses

## Amazon EC2
* Elastic cloud compute
* provides virtual amchines in the cloud, giving you full control over your OS
### What is an Amazon Machine Image
* Template used to build a virtual machine
* Snapshot of a machine and it's data
* Comparable to a Vagrant virtual box. Both have an OS but AMI's also provide the state of machine - hard drive

## What is a Bastion Server?
* A bastion is a special purpose server instance that is designed to be the primary access point from the Internet and acts as a proxy to your other EC2 instances.

## Auto scaling and load balancers
