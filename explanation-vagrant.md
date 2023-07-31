# Explanation of Ansible Playbook and Roles

## Step 1: Directory Structure

- `playbook.yml`: This is the main Ansible playbook that includes roles and executes the tasks for provisioning the Vagrant VM, setting up Docker, and running the Docker Compose.

- `Vagrantfile`: This Vagrantfile sets up the Vagrant VM with Ubuntu 20.04.

- `docker-compose.yml`: This file defines the services and configurations required to run the application using Docker Compose.

- `roles/`: This folder contains individual roles for different tasks in our project.

## Step 2: Vagrant VM and Docker Setup

We used the `Vagrantfile` to provision a Vagrant virtual machine with Ubuntu 20.04. This VM will serve as our target host for Ansible automation.

## Step 3: Ansible Playbook

In the `playbook.yml`, The playbook includes the following roles:

- `common`: This role installs required packages, such as git, on the Vagrant VM.

- `mongodb`: This role installs Docker and Docker Compose on the Vagrant VM to prepare it for running containers.

- `clone_repo`: This role clones the entire repository from GitHub to the `/vagrant/yolo_repo` directory on the Vagrant VM. This role ensures that both the `client` and `backend` folders are available in the VM.

- `backend`: This role copies the files from the `/vagrant/yolo_repo/backend` folder to the `/vagrant/backend` folder in the Vagrant VM. It then builds the Docker image for the backend application using the existing Dockerfile in the `backend` folder.

- `client`: This role copies the files from the `/vagrant/yolo_repo/client` folder to the `/vagrant/client` folder in the Vagrant VM. It then builds the Docker image for the client application using the existing Dockerfile in the `client` folder.

- `docker-compose`: This task runs the `docker-compose up -d` command to launch the Docker containers defined in the `docker-compose.yml` file.


