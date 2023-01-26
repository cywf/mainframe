# Alt-F4 Mainframe

Alt-F4 Mainframe is a powerful and advanced platform for hosting Capture The Flag (CTF) competitions. Using Terraform, we can quickly spin up and spin down the infrastructure required for hosting CTF matches, with the help of Zerotier network virtualization software.

## Features

- Server vs Server competition format
- Quick spin up and spin down of infrastructure using Terraform
- Network virtualization using Zerotier
- Support for teams of 4 players
- Robust and scalable infrastructure
- Backend and frontend functionality (Backend functionality will be our main focus)

## Getting Started

To get started with Alt-F4 Mainframe, you will need to have the following software installed:

- Terraform (https://www.terraform.io/)
- Zerotier (https://www.zerotier.com/)
- Ansible (https://www.ansible.com/)

You can then clone the repository and use Terraform to provision the infrastructure.

## Index

- [Introduction](#introduction)
- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Usage](#usage)
- [Terraform Configuration](#terraform-configuration)
  - [Creating Virtual Networks](#creating-virtual-networks)
  - [Provisioning Servers](#provisioning-servers)
- [Ansible Configuration](#ansible-configuration)
  - [Installing Software](#installing-software)
  - [Configuring Services](#configuring-services)
- [Scaling and Updates](#scaling-and-updates)
- [Troubleshooting](#troubleshooting)
- [Contribution](#contribution)
- [License](#license)

### Introduction

Alt-F4 Mainframe is a powerful and advanced platform for hosting Capture The Flag (CTF) competitions. Using Terraform, we can quickly spin up and spin down the infrastructure required for hosting

### Features

- Server vs Server competition format
- Quick spin up and spin down of infrastructure using Terraform
- Network virtualization using Zerotier
- Support for teams of 4 players
- Robust and scalable infrastructure
- Backend and frontend functionality (Backend functionality will be our main focus)

### Getting Started

#### Prerequisites
- Terraform (https://www.terraform.io/)
- Zerotier (https://www.zerotier.com/)
- Ansible (https://www.ansible.com/)

#### Installation
1. Clone the repository: 
```bash
git clone https://github.com/alt-f4-society/mainframe.git
```
2. Change into the project directory:
```bash
cd mainframe
```
3. Initialize and download the required Terraform modules:
```bash
terraform init
```

#### Usage

Once you have installed the prerequisites and cloned the repository, you can use Terraform to provision the infrastructure by running the following command:

```bash
terraform apply
```

This command will create the virtual networks and provision the servers required for the CTF platform.

Once the infrastructure is provisioned, you can use Ansible to configure the servers and install the required software.

### Terraform Configuration

Terraform is used to provision the infrastructure required for the Alt-F4 Mainframe CTF platform. It is used to create virtual networks and provision servers.

#### Creating Virtual Networks

Zerotier is used to create virtual networks that are used to connect the CTF servers. You can create a virtual network by running the following command:

```bash
terraform apply -target=module.zerotier
```

This will create a virtual network and provide you with a network ID that can be used to join other servers to the network.

#### Provisioning Servers

Once the virtual network is created, you can use Terraform to provision servers that will be used for the CTF competitions. You can provision servers by running the following command:

```bash
terraform apply -target=module.servers
```

This will provision servers, and also join them to the virtual network created above.

You can also customize the Terraform code to create different types of servers or adjust the number of servers to meet your needs.

It's important to note that provisioning servers will also install the necessary software and configure the servers, this is done with Ansible.

### Ansible Configuration

Ansible is used to configure the servers that are provisioned using Terraform. It is used to install software and configure services.

#### Installing Software

Ansible is used to install the necessary software on the servers. This includes software such as Apache, PHP, MySQL, and other software required for the CTF platform. You can install software by running the following command:

```bash
ansible-playbook -i hosts site.yml
```

This command will install the software on all of the servers in the inventory file (hosts).

#### Configuring Services

Ansible is also used to configure the services that are installed on the servers. This includes configuring Apache, PHP, MySQL, and other services required for the CTF platform. You can configure services by running the following command:

```bash
ansible-playbook -i hosts site.yml --tags=configure
```

This command will configure the services on all of the servers in the inventory file (hosts).

You can also customize the Ansible code to install different software or configure services to meet your needs.

### Scaling and Updates

The Alt-F4 Mainframe CTF platform is designed to be scalable and easily updatable. 

#### Scaling

Scaling the infrastructure is done by modifying the Terraform code. You can increase or decrease the number of servers or adjust the resources allocated to the servers. Once you have made the necessary changes, you can use Terraform to apply the changes by running the following command:

```bash
terraform apply
```


#### Updates

Updating the software and services on the servers is done using Ansible. You can update the software by running the following command:

```bash
ansible-playbook -i hosts site.yml
```

This command will update the software on all of the servers in the inventory file (hosts).

You can also customize the Ansible code to update specific software or services to meet your needs.

It's important to note that updates should be tested in a non-production environment before applying them to production servers.

### Troubleshooting

If you encounter any issues while setting up or using the Alt-F4 Mainframe CTF platform, here are some common troubleshooting steps that may help resolve the issue:

- **Terraform**: Check the Terraform logs for any errors. You can view the logs by running the following command:

```bash
terraform show -json
```

- **Ansible**: Check the Ansible logs for any errors. You can view the logs by running the following command:

```bash
ansible-playbook -i hosts site.yml --list-tasks
```

- **Zerotier**: Check the Zerotier logs for any errors. You can view the logs by running the following command:

```bash
zerotier-cli info
```

- **Software**: Check the logs for the software that is causing the issue. You can view the logs by running the following command:

```bash
tail -f /var/log/[software].log
```

If the issue persists, please consult the documentation or reach out to the community for help.

### Contribution

We welcome contributions to the Alt-F4 Mainframe CTF platform. If you would like to contribute, please follow these guidelines:

- **Fork** the repository on GitHub.
- **Clone** the repository to your local machine.
- **Create** a new branch for your changes.
- **Make** your changes and **test** them.
- **Commit** your changes and **push** them to your fork.
- **Create** a new **pull request** to the **main** repository.

Please make sure that your changes are well tested and do not break any existing functionality.

We are looking forward to your contributions!

This is in no way affiliated with zerotier, terraform, ansible, or any other software used in this project. However, if you are a member of the zerotier, terraform, or ansible team and would like to help us scale this project, please reach out to us, as we are currently looking for sponsors to help us scale this project.