# VirtualBox Vagrant Environment Setup

This guide provides an overview and instructions for setting up a development environment using Vagrant with VirtualBox as the provider. The setup includes multiple Ubuntu VMs, each configured with Docker, Kubernetes tools, an SSH server, HTTPD (Apache2), and Curl.

## Overview

The `Vagrantfile` defines a Vagrant environment with the following configurations:

- **VM Configuration**: Creates 3 Ubuntu VMs, each with 4GB of RAM and 4 CPU cores.
- **Networking**: Configures two network adapters for each VM; one for a private network allowing inter-VM communication, and another for bridged networking allowing VM-host communication.
- **Provisioning**: Installs necessary packages including Docker, Kubernetes command-line tool `kubectl`, HTTPD (Apache2), Curl, and the SSH server. User accounts `ola` and `standard` are created, with `ola` given sudo access without a password requirement.
- **SSH Access**: SSH keys are added to `ola`'s `authorized_keys` for secure access.

## How to Run

1. **Install Vagrant and VirtualBox**: Ensure you have both [Vagrant](https://www.vagrantup.com/downloads) and [VirtualBox](https://www.virtualbox.org/wiki/Downloads) installed on your system.

2. **Clone the Vagrant Project**: Clone or download the project containing the `Vagrantfile` to your local machine.

3. **Start the Vagrant Environment**:
    - Open a terminal and navigate to the project directory.
    - Run `vagrant up` to create and provision the VMs. Vagrant will automatically use VirtualBox as the provider.

4. **Accessing VMs**:
    - Use `vagrant ssh 'vm-name'` (run command without the quotes) to SSH into the VM.
    - The user `ola` can be accessed with SSH using the provided keys.

5. **Stopping VMs**:
    - Run `vagrant halt` to stop the VMs.

6. **Cleaning Up**:
    - Run `vagrant destroy` to permanently remove the VMs from your system.

For more information on Vagrant commands and configurations, visit the [Vagrant documentation](https://www.vagrantup.com/docs).

