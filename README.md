# Project Network Configuration README.md

## Overview

This outlines the configurations for a network setup designed to
segment different types of traffic into management, server, and client VLANs,
ensuring good, organized, and efficient networking. 

This setup
includes configurations for a router (`ttr1`), 2 switches (`ttsw1`),(`ttsw2`) and an access
point (`ttap1`), along with DHCP services currently on the router, VLAN setup,
and secure access protocols.

It is planned to expand the network, and include redundancy in form of link
aggregation and HSRP. Dedicated DHCP, Print, DNS, and more.

## Equipment and Configurations

### Router Configuration (`ttr1`)

- **Hostname**: `ttr1`
- **DHCP Settings**:
  - Excludes specific addresses making sure critical ips are excluded from the scope.
  - Separate DHCP pools for CLIENT and SERVER networks.
  - Specifies default routers, DNS servers, and lease times.
- **Interfaces**:
  - Subinterfaces Configured with IP addresses and NAT settings for WAN and LAN interfaces.
  - VLANs for management (VLAN10), server (VLAN20), and client (VLAN30) with appropriate addressing.
- **Security**:
  - A small subnet with only needed network size.
  - Access control lists to permit all traffic. (Not safe).
  - RSA keys generated for SSH, ensuring secure management access.

### Switch Configuration (`ttsw1`)

- **Hostname**: `ttsw1`
- **VLAN Setup**:
  - VLAN10 (MGMT), VLAN20 (Server), and VLAN30 (Client) with descriptive names and purposes.
- **Port Security**:
  - Applied on all interface ranges to restrict the network based on MAC addresses.
- **Interface Configurations**:
  - Trunking setup on GigabitEthernet interfaces to allow VLAN traffic.
  - Access port configurations for specific VLANs, supporting various network needs, including WAP and server connections.

### Access Point Configuration (`ttap1`)

- **Hostname**: `ttap1`
- **DHCP Relay**: Excluded addresses and helper address configured for the client network.
- **Wireless Configuration**:
  - SSID setup with WPA2 security for guest access.
- **Interface**:
  - BVI1 configured with IP addressing and helper address for DHCP relay.

### Server VLAN Details

- Hosts a Proxmox server that currently runs a VM with a NixOS flake for a VPN
  server. This setup provides a secure, virtualized environment for the VPN
  service. Also gives us access to the project from wherever we are.

## Network Services

- **DHCP**: Dynamic Host Configuration Protocol for IP address assignment.
- **NAT**: Network Address Translation for Internet access across the network.
- **VLAN**: Virtual Local Area Networks for segmenting network traffic.
- **SSH**: Secure Shell for encrypted remote management.
- **VPN**: Secure connection to our project. 

## Security Features

- **Access Control Lists (ACLs)**: To permit authorized traffic.
- **Port Security**: To prevent unauthorized access based on MAC addresses.
- **WPA2**: Secure Wi-Fi access.
- **VPN**: Using our vpn to avoid opening ports to the outside network.

## Thoughts

This network setup provides a robust template for managing network requirements,
and dynamic IP address management. The inclusion of a virtualized VPN server
including secure remote access, efficient traffic segmentation, further enhances
the network's capabilities, offering secure remote connectivity options.

