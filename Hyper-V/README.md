# Hyper-V Vagrant Environment Setup

This document details the setup of a Vagrant environment with Hyper-V as the provider. It includes the creation of 5 VMs, each configured with a set of development tools, Docker, Kubernetes tools, and more.

## Overview

The provided `Vagrantfile` automates the setup of:

- **VM Configuration**: 5 VMs based on Ubuntu, each with customized hostnames derived from their IP addresses for easy identification.
- **Networking**: Private networking is configured for inter-VM communication, with static IP addresses assigned to each VM.
- **User Setup**: Creates users `ola` and `standard`, with SSH keys configured for `ola` to enable secure SSH access.
- **Development Tools**: Installs Docker, `kubectl` for Kubernetes, Apache HTTP Server (`httpd`), and Curl across all VMs. The first VM additionally receives Ansible, Terraform, and Vagrant for infrastructure and deployment automation.

## How to Run

1. **Install Vagrant**: Download and install [Vagrant](https://www.vagrantup.com/downloads).

2. **Enable Hyper-V**: Ensure Hyper-V is enabled on your Windows system. This might require turning on features in the Windows Features settings or through PowerShell.

3. **Setup and Configuration**:
    - Clone or download the project containing the `Vagrantfile`.
    - Open a PowerShell terminal as Administrator in the project directory.

4. **Launch VMs**:
    - Execute `vagrant up --provider=hyperv` to start and provision the VMs. Specify `--provider=hyperv` to ensure Vagrant uses Hyper-V.

5. **SSH Access**:
    - Use `vagrant ssh vm1` to SSH into the first VM (substitute `vm1` with the appropriate VM name for others).
    - Access for `ola` is configured via the provided SSH keys.

6. **Management**:
    - To stop the VMs, run `vagrant halt`.
    - To remove the VMs from Hyper-V, execute `vagrant destroy`.

Please refer to the [Vagrant documentation](https://www.vagrantup.com/docs) for detailed information on Vagrant usage and command options.

