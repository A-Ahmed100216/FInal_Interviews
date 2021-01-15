# DevOps tools

## Vagrant
* Tool for building and managing virtual environments.
* Open source Linux distribution
* Written in ruby
* Vagrant boxes - preloaded vagrant files that create virtual machines. Usually just an OS.
* The easiest way of adding a box is looking up from the catalog. There are many boxes available including ubuntu.

### What is Virtualisation
* Virtualisation is the creation of a virtual object such as an operating system, server, storage etc.
* With virtualisation, a guest OS is abstracted away from the underlying hardware or software. A hypervisor is a tool used to achieve virtualisation.
* A hypervisor is a layer of software which emulates the underlying hardware of a physical resource and separate the constituents so they can be used by the virtual environment.
* While the performance of a virtual machine is not comparable to an actual computer, it is usually sufficient as a virtual machine does not need all the functionality of the base computer.

## Jenkins
* Open source automated ci/cd server
* A tool which simplifies the establishment of a continuous integration and continuous delivery, core aspects of DevOps.

## What is IAC?
* Infrastructure as code
* Managing and provisioning data through machine readable files.
* Manage IT infrastructure with configuration files

1. Speed- Quickly deploy infrastructure by running scripts.
2. Consistency - Always deploy the same configuration
3. Accountability - Can have version control so pinpoint any sources if failure.
4. Efficiency - Deploy infrastructure in many stages, raise team productivity.
5. Lower Cost - Employ cloud computing alongside IAC therefore significantly reducing costs.

## Ansible
* Automates cloud provisioning, configuration management, app deployment and more.
* Uses YAML syntax
* Requires Python on Linux hosts and PowerShell 3 on Windows hosts.
* Push Configuration Tool - Doesn't require an agent to be installed on the host. The server pushes the configuration to the nodes. (Chef and Puppet are opposite, they use the pull configuration)
* Platform Agnostic - With the Ansible abstraction layer, can run code in any environment for any OS and it will know how to perform the operation.
* Architecture:
  * Local Machine - This is where Ansible is installed
  * Module - Collection of configuration code files i.e. playbooks
  * Inventory - Document which groups nodes under specific labels
  * Nodes - The systems to be configured. Controlled by the local machine
  * Local Machine connects to nodes using SSH client


# Packer
* Open source tool
* Creates machine images for multiple platforms.
* Does not replace configuration management tools like Chef or Puppet, rather, it works in conjunction with them.
* Declared in a JSON file
## What is an AMI?
* Templates used to build a virtual machine
* Snapshot of a machine and it's data
* Comparable to a Vagrant virtual box. Both have an OS but AMI's also provide the state of machine - hard drive


## Terraform
* Infrastructure Orchestration tool - Allows you create IAC for deployment on any cloud.
### Why?
* Scale up and down to meet customer demand.
* Terraform is cloud agnostic i.e. allows you to automate infrastructure from multiple cloud providers simultaneously.
* Immutable Infrastructure model:
  * Servers are not modified after deployment, instead new servers and built from a template.
  * Why? Eliminate configuration drift - running servers become increasingly different over time due to manual changes, updates etc.


### What is Docker?
* Docker is an open-source platform used for containerisation.
* It enables us to separate applications from the infrastructure.
* It allows us to deliver software faster
* Docker is written in GO language.
# What is a container?
* A standardised unit of software.
* Packages code and all its dependencies so applications can run quickly and reliably from one environment to another.
* They include everything needed to run an app (code, runtime, system tools, libraries, settings).  

# VMs vs Containers
* Docker is lightweight and user-friendly.
* Docker shares the resources of the OS as opposed to building a new OS.
* Docker engine connects the container with OS and only uses the resources required.
* VM run on a hypervisor, create own OS. Containers run on any OS.
* Hypervisor - layer of software which emulates the underlying hardware of a physical resource and separate the constituents so they can be used by the virtual environment.
* VMs more secure than Containers


# Microservices
* Architectural approach wherein services are split up into smaller nodes, called microservices.
* Services built around business capabilities so each microservice typically addresses one business capability.
* Split your application into smaller, inter-connected services that are:
  * Highly maintainable and testable
  * Loosely coupled
  * Independently deployable
  * Organised around business capabilities
  * Owned by small teams

# Kubernetes
* Container Orchestration Service
