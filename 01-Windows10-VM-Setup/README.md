# Windows 10 VMware Lab Setup

## Installation

I started building my cybersecurity home lab using VMware.

Before installing Windows 10, I configured the VMware network settings by adding a second network adapter and setting it to *Host-only*.

I did this because I wanted my lab machines to have a private network for communication while keeping internet access separate through NAT.

## Network Setup

The network adapters were configured as:

- *NAT:* Used for internet connection and Windows updates.

- *Host-only:* Used for private communication between my virtual machines inside the lab environment.

After configuring the network adapters, I continued with the Windows 10 installation.

## Windows Setup

During the Windows setup process, I selected the local account option and created my administrator account:

*Username:* CsgAdmin

This account will be used for learning Windows administration and security practices inside my lab.

## Windows Updates

After completing the installation, the next step was updating Windows.

I checked for updates and allowed Windows to download and install the latest updates and security patches.

While the updates were running, I started checking the network configuration inside the virtual machine.

## Network Verification

I used the command:

```cmd
ipconfig
```
The ipconfig command displays the network adapters and IP information available on the system.

I learned that the adapter showing a Default Gateway was my NAT connection because it provides internet access to the virtual machine.

The Host-only adapter is used for private communication between lab machines and normally does not have a Default Gateway.

## What I Learned

This setup helped me understand how virtual machines can use different network connections depending on their purpose.

NAT allows the VM to access the internet, while Host-only creates a private network for safely building and testing a cybersecurity lab environment.

This is the first step in building my CSG Security Lab.

# Connectivity Test

After verifying the network configuration, I tested internet connectivity from inside the virtual machine.

I used the following commands:

```cmd
ping 8.8.8.8
ping google.com
```

## Results

Both commands completed successfully with 0% packet loss, confirming that network connectivity was working correctly.

- ping 8.8.8.8 confirmed that the virtual machine had internet connectivity.
- ping google.com confirmed that DNS name resolution was working correctly.

## What I Learned

This test confirmed that my NAT adapter was configured correctly and that the virtual machine could communicate with external networks. I can now download Windows updates, install cybersecurity tools, and access GitHub for future lab work.
