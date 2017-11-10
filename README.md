# Configuration Management With Ansible

This repo contains demo for Nairobi Google DevFest


# Folders

This repo has the following folders and files

```txt
.
├── LICENSE
├── README.md
├── Vagrantfile
├── ansible
│   ├── deploy.yml
│   ├── inventory
│   │   ├── hosts
│   │   └── vars
│   │       └── variables.yml
│   ├── provision.yml
│   ├── templates
│   │   └── default.j2
│   └── variables.yml
├── ansible.cfg
├── bin
│   ├── deploy
│   └── setup
└── ssh.config

```

The tree above shows the folders and files to be used in this demo

## ansible/

This folder holds all the ansible related files, these include inventory, variables and playbooks

```txt
├── ansible
│   ├── deploy.yml
│   ├── inventory
│   │   ├── hosts
│   │   └── vars
│   │       └── variables.yml
│   ├── provision.retry
│   ├── provision.yml
│   ├── templates
│   │   └── default.j2
│   └── variables.yml
```

## inventory/

This folder contains variables and host files used by ansible playbooks

```txt
├── inventory
│   ├── hosts
│   └── vars
│       └── variables.yml
```

## vars

This folder contains variables file. This variables will be used by the playbooks

```txt
└── vars
    └── variables.yml

```

## Templates

This folder contains templates used by the playbooks to copy files to the server.
```
├── templates
│   └── default.j2

```

# Files

## Playbooks

This repo contains 3 playbooks namely;

- `variables.yml` - this playbook will be used to load variables
- `provision.yml` - This playbook is used to provision (setup) server for app deployment
- `deploy.yml`    - This playbook is used to build and deploy the app to the server

## Inventory

This repo has two inventory files

- `variables.yml` - This inventory files contains all the variables required in the playbooks
- `hosts`         - This inventory file contains the hosts domains/ip addresses ansible will use to access the server

## Templates

This repo contains only 1 template file

- `default.j2` - This contains the nginx configuration template

## Configuration files

These are files used to setup both ansible vagrant

- `Vagrantfile` - Contains vagrant VM configurations
- `ansible.cfg` - Contains information ansible will use to run the playbooks e.g inventory, ssh options e.t.c
- `ssh.config` -  Contains ssh configuration information


## Scripts

There are two bash scripts used to abstract ansible commands

- `bin/setup` - This scripts runs the provision playbook
- `bin/deploy` - This script runs the deploy playbook

# Usage

Below are the steps on how to use the scripts

## Setup Demo Server

The Demo server used in this exercise is provisioned using vagrant, Ensure you have it installed. Run vagrant up to start the server

```bash

$ vagrant up

```

## Run playbooks

After the server is up and running- you can confirm this by running vagrant status. Use the scripts in the bin folder to run both provision and deploy playbooks.

```bash

# provision your server (setup server for app deployment)

$ chmod u+x bin/setup

$ bin/setup ( you can add -vvv for verbose)


# Deploy the app from github

$ chmod u+x bin/deploy

$ bin/deploy ( you can add -vvv for verbose)

```

