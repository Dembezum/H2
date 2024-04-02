# GNS3 Server on Ubuntu

This repository contains configuration files for setting up a GNS3 server on an
Ubuntu system. GNS3 is a network software emulator that allows the combination
of virtual and real devices, used to simulate networks.

## Prerequisites

- Ubuntu Server 20.04
- GNS3 2.2.44.1
- Troubleshooting knowledge
- Some linux knowledge 

When saying some linux knowledge is needed, what i really mean is that you
should know which tools can be used for setting up what is needed such as -
- [Systemd]() to manage services
- A text editor like Vim or Nano
- cat
- 

## Installation

### Step 1: Install Ubuntu server

Follow this *[guide](https://ubuntu.com/tutorials/install-ubuntu-server#1-overview)* if
needed. The installation proccess should be simple and easy.


### Step 2: Install GNS3

When setting up a GNS3 server there are a couple of things you should keep in
mind. Firstly you should think about what your requirements are.
- How many [appliances](https://gns3.com/marketplace/appliances)
- How many users there will be
- How the [virtual network Bridges](https://computingforgeeks.com/how-to-create-and-configure-bridge-networking-for-kvm-in-linux/) should be configured
