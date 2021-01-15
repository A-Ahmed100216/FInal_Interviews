# Development Environments - Vagrant

## What is Virtual Box?
* Virtual box is an open source hosted hypervisor used for the purposes of virtualisation.

## What is Virtualisation?
* Virtualisation is the creation of a virtual object such as an operating system, server, storage etc.
* With virtualisation, a guest OS is abstracted away from the underlying hardware or software. A hypervisor is a tool used to achieve virtualisation.
* A hypervisor is a layer of software which emulates the underlying hardware of a physical resource and separate the constituents so they can be used by the virtual environment.
* While the performance of a virtual machine is not comparable to an actual computer, it is usually sufficient as a virtual machine does not need all the functionality of the base computer.

## What is Vagrant?
* Open source Linux distribution
* Written in ruby
* Vagrant boxes - preloaded vagrant files that create virtual machines. Usually just an OS.

## Main Commands
* `vagrant init` - Creates a vagrantfile based on a box in the Vagrant Cloud. This command can also be run as follows:
  * `vagrant init <box>` - initialises a specific box
* `vagrant up` - get the box to run.
* `vagrant destroy` - delete a box- everything inside is lost
* `vagrant ssh` - login to the virtual machine
* `logout` - log out of the virtual machine
* `vagrant suspends` - saves contents of box
