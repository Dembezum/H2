# Linux Project week

This is our linux Project. Here we will shortly go over how our infrastructure
will be, which services to run, the servers, and which operating systems we use.


## Infrastructure

The servers will be hosted on Proxmox. This is partly because of the simplicity
of managing multiple machines, creating our network infrastructure is also
fairly simple using proxmox, and it's open source, free and a great built tool.

> Proxmox is a super great operating system to use for hosting multiple servers,
> vms and containers. It's based on Debian and is a Type 1 hypervisor.
> We could use something proprietary, but licensing will be against our liking.

### Servers

1. Proxmox host
2. NixOs DHCP Server
3. NixOs VPN Server
4. NixOs or Debian DNS Server
5. OPNsense Router
7. TrueNAS (Optional)
8. Nixos Client 
9. Ubuntu Client
10. Archlinux Client (Optional)


#### Operating systems

Lets start with the Proxmox server, this is a a HP Server running proxmox as the
operating system.

As you have seen, most of these machines will be running NixOs. This is due to
the amazing way nix works. One of the many beauties with NixOs is the able to
declare the entire system before building it. This means that you can have a set
of files in which the system is configured. This could be how the netwokring is
done, i.e ip's, DNS, firewall etc.

You could also declare which programs will be installed, and to which users and
with declared permissions as well. You will be able to have the entire system
configured before you even boot up. When you boot up you import the
configuration you have created and build it. 

You will now forever be free of "this works on my machine only", or "It doesn't
work on my machine". It will. Always.

