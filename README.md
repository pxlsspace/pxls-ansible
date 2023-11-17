# pxls.space Ansible Playbook

This Ansible playbook automates the setup of a machine for running [pxls.space](https://pxls.space/), a collaborative pixel art platform. The playbook is designed for a target host group named "pxls"

## Playbook Structure

### 1. Machine Setup

#### Pre-tasks
- **Who are we?!**: Identifies the current user.
- **Set a fact with the user name**: Captures the user name.
- **Ensure apt cache is updated**: Updates the APT package cache.
- **Upgrade existing packages**: Upgrades existing packages.

#### Tasks
- **Install OS prerequisites**: Installs common dependencies.
- **Create directory for apt keyrings**: Sets up a directory for APT keyrings.
- **Add Nodesource GPG key**: Adds the Nodesource GPG key.
- **Add Nodesource repository**: Adds the Nodesource repository.
- **Add PHP 7.x repository**: Adds the PHP 7.x repository.
- **Update APT package cache after adding repositories**: Updates the APT package cache.

### 2. Install Software

#### Tasks
- **Install Node.js v{{ node_version }}.x LTS**: Installs Node.js.
- **Install NGINX Webserver**: Installs NGINX.
- **Install PostgreSQL**: Installs PostgreSQL.
- **Install PHP packages**: Installs PHP packages.
- **Install OpenJDK JRE, JDK and Maven**: Installs OpenJDK, Maven, and Java packages.

### 3. Setup pxls.space

#### Tasks
- **Create pxls build directory**: Sets up the pxls build directory.
- **Create pxls target directory**: Sets up the pxls target directory.
- **Install pxls.space**: Clones the pxls.space repository from [GitHub](https://github.com/pxlsspace/Pxls.git).

## Usage

1. Modify the variables in `vars/main.yml` to customize the installation.
2. Run the playbook using the following command:
   ```bash
   ansible-playbook -i inventory.yml pxls-setup.yml
   ```

Note: Ensure you have Ansible installed and a valid inventory file (`inventory.yml`) with the "pxls" host group defined.

Feel free to contribute or report issues on [GitHub](https://github.com/pxlsspace/pxls-ansible). Happy pixeling!