# Implement Ansible Roles in Playbooks

This repository demonstrates the implementation of Ansible roles and playbooks for automated server configuration management, specifically focusing on Apache and PHP installation across different Linux distributions.

## Project Overview

This project showcases how to use Ansible to automate the installation and configuration of Apache web server and PHP across different Linux distributions (RedHat/CentOS and Debian/Ubuntu) using a single playbook with dynamic package names.

## Repository Structure

```
.
├── ansible.cfg         # Ansible configuration file
├── inventory          # Inventory file with host definitions and variables
└── install_apache.yml # Main playbook for Apache and PHP installation
```

## Features

- Cross-distribution compatibility (works with both RedHat and Debian-based systems)
- Dynamic package name handling using variables
- Automated installation of Apache and PHP
- Automatic package cache update during installation

## Prerequisites

- Ansible installed on the control node
- SSH access to target servers
- Target servers defined in the inventory file

## Usage

1. Ensure your target servers are listed in the `inventory` file with appropriate variables:
   ```ini
   192.168.56.110 apache_package=httpd php_package=php         # For RedHat/CentOS
   192.168.56.111 apache_package=apache2 php_package=libapache2-mod-php  # For Debian/Ubuntu
   ```

2. Run the playbook:
   ```bash
   ansible-playbook -i inventory install_apache.yml
   ```

## Variables

The playbook uses the following variables that should be defined per host in the inventory:

- `apache_package`: The name of the Apache package (httpd for RedHat/CentOS, apache2 for Debian/Ubuntu)
- `php_package`: The name of the PHP package (php for RedHat/CentOS, libapache2-mod-php for Debian/Ubuntu)

## Contributing

Feel free to submit issues, fork the repository, and create pull requests for any improvements.

