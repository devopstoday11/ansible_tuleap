# Ansible : Playbook Tuleap

The aim of this project is to deploy am all in one Tuleap server on a Linux Vagrant instance.

This project can be used for demo purpose.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

What things you need to run this Ansible playbook :

*   [Vagrant](https://www.vagrantup.com/docs/installation/) must be installed on your computer
*   Update the Vagrant file based on your computer (CPU, memory), if needed
*   Update the operating system to deploy in the Vagrant file (default: CentOS 7)
*   Install the [Vagrant HostManager plugin](https://github.com/devopsgroup-io/vagrant-hostmanager) :

```
$ vagrant plugin install vagrant-hostmanager
```
*   Download the Ansible requirements:

```bash
$ ansible-galaxy install -r requirements.yml
```

### Usage

A good point with Vagrant is that you can create, update and destroy all architecture easily with some commands.

Be aware that you need to be in the Vagrant directory to be able to run the commands.

#### Deployment

To deploy Tuleap on a Vagrant instance, just run this command :

```bash
$ vagrant up
```

If everything run as expected, you should be able to list the virtual machine created :

```bash
$ vagrant status

Current machine states:

tuleap01                   running (virtualbox)
```

If everything run as expected, you should be able to reach the Tuleap web interface : https://tuleap.local/

The default admin password should be displayed in the last Ansible task.

#### Destroy

To destroy the Vagrant resources created, just run this command :

```bash
$ vagrant destroy
```

### How-To

This section list some simple command to use and manage the playbook and the Vagrant hosts.

#### Update with Ansible

To update the Tuleap configuration with Ansible, you just have to run the Ansible playbook tuleap.yml with this command :

```bash
$ ansible-playbook tuleap.yml
```

#### Update with Vagrant

To update the Tuleap configuration with Vagrant, you just have to run provisioning part of the Vagrant file :

```bash
$ vagrant provision
```

#### Connect to Vagrant instance

To be able to connect to a Vagrant instance, you should use the CLI which is configured to automatically use the default SSH key :

```bash
$ vagrant ssh tuleap01
```

## Author

Member of Wikitops : https://www.wikitops.io/

## Licence

This project is licensed under the Apache License, Version 2.0. For the full text of the license, see the LICENSE file.
