# Install Omada Controller on Ubuntu

[![lint](https://github.com/kdpuvvadi/omada-ubuntu-ansible/actions/workflows/lint.yml/badge.svg)](https://github.com/kdpuvvadi/omada-ubuntu-ansible/actions/workflows/lint.yml)

Playbook tested on follwoing host distributions

* Debian 8, 9 & 10
* Ubuntu 18.04, 20.04

Tested on Control Node Ubuntu 20.04 LTS. Ansible 2.11.6.

## Setup Ansible

* Install pip `sudo apt install python3-pip -y`.
* install ansible with pip `pip install ansible`.

## Installed Packages

* `OpenJDK 1.8 Headless`   -- Omada only supports Java 8
* `MongoDB 3.6`    -- Omada Supports 3.4 to 4.0
* `curl`
* `jsvc`
* `tar`

## Getting Started

* Clone the repo  `git clone https://github.com/kdpuvvadi/omada-ubuntu-ansible.git omada-ubunt-ansible`.
* Install requirements `ansible-galaxy collection install -r requirements.yml`.
* copy `inventory.ini.j2` to `inventory.ini`.
* Change necessary changes to inventory.
* copy `vars.yml.j2` to `vars.yml`.
* Change the variable based on your preferences.

## Run the playbook

* Run `ansible-playbook main.yml`.
* append `-K` if you need password for `sudo`, `ansible-playbook main.yml -K`.

## Post Install

* Omada controller will be avaiable on `https://HOST-IP:8088/`  or `https://HOST-IP:8043/`.

## Ports

* From v5.0.29 Adoption port has been changed to `29814/tcp`.
* To work properly Omada needs these ports `8088, 8043, 27001, 27002, 29810, 29811, 29812, 29813 and 29814` to be open.

## Omada Service on host

* `sudo tpeap status`     -- show the status of Controller;
* `sudo tpeap start`     -- start the Omada Controller;
* `sudo tpeap stop`     --stop running the Omada Controller.

## Uninstall 

If you wish to uninstall Omada controller, ssh in to the server and run `sudo apt remove omadac`
