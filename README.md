
# Vagrant Environment Setup Guide

This guide covers the setup of development environments using Vagrant with either Hyper-V or VirtualBox as the provider. Each environment configures multiple virtual machines (VMs) with Ubuntu, installs essential development tools, and sets up networking and SSH access.

## Overview

Two `Vagrantfile` scripts are provided:
- One for **Hyper-V**: Tailored for environments running on Windows with Hyper-V enabled.
- One for **VirtualBox**: Suitable for cross-platform use where VirtualBox is preferred or required.

Each script dynamically creates VMs, configures them with a private network, installs software packages such as Docker, Kubernetes CLI tools (`kubectl`), HTTPD (Apache), and Curl. The first VM in each setup receives additional tools: Ansible, Terraform, and Vagrant.

### Hyper-V Script Features
- Configures VMs with Hyper-V.
- Names VMs using a convention based on their assigned IP addresses for easy identification.
- Applies a specific IP address to the first VM and sequential IP addresses to others.

### VirtualBox Script Features
- Configures VMs with VirtualBox.
- Utilizes two network adapters per VM for enhanced networking capabilities.
- Similar software installation and user setup as the Hyper-V script.

## Prerequisites
- **For Hyper-V**: Windows 10/11 Pro, Enterprise, or Education with Hyper-V enabled.
- **For VirtualBox**: Windows, macOS, or Linux with VirtualBox installed.
- **General**: Git (for cloning the repository) and Vagrant installed on your system.

## How to Run

1. **Clone the Repository**: Clone the GitHub repository containing the Vagrant scripts to your local machine.
    ```
    git clone <repository-url>
    cd <repository-directory>
    ```

2. **Choose Your Provider**:
    - For Hyper-V, ensure Hyper-V is enabled on your system.
    - For VirtualBox, ensure VirtualBox is installed.

3. **Start the Vagrant Environment**:
    - Navigate to the directory containing the desired `Vagrantfile` (Hyper-V or VirtualBox).
    - Run the following command to initiate and provision the VMs:
        ```bash
        vagrant up --provider=hyper-v # For Hyper-V
        ```
        or
        ```bash
        vagrant up # For VirtualBox (default provider)
        ```

4. **Accessing VMs**:
    - Use `vagrant ssh <vm-name>` to SSH into a specific VM. The VM names follow the convention defined in the respective `Vagrantfile`.

5. **Stopping VMs**:
    - To halt the VMs without destroying them, use:
        ```bash
        vagrant halt
        ```

6. **Cleaning Up**:
    - To permanently remove the VMs and clean up all resources, use:
        ```bash
        vagrant destroy
        ```

## Useful Vagrant Commands

- `vagrant up`: Starts and provisions the VM(s) according to the `Vagrantfile`.
- `vagrant halt`: Stops the VM(s).
- `vagrant reload`: Restarts and re-applies any changes to the `Vagrantfile` to the VM(s).
- `vagrant ssh <vm-name>`: Connects to the VM via SSH.
- `vagrant destroy`: Stops and deletes all resources created during the machine creation process.

## Customization

You can customize the VM configurations, networking, and provisioned software by editing the `Vagrantfile`. For detailed documentation on Vagrant's features and configuration options, visit the [official Vagrant documentation](https://www.vagrantup.com/docs).

---

Ensure you replace `<repository-url>` and `<repository-directory>` with the actual URL and directory name of the GitHub repository where your Vagrant scripts are stored. This README provides a comprehensive guide for users to set up, manage, and understand their Vagrant environments.
