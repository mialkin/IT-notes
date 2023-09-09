# Ansible

Ansible is a:

- simple automation language that can perfectly describe an IT application infrastructure in Ansible Playbooks.
- automation engine that runs Ansible Playbooks.

## Table of contents

- [Ansible](#ansible)
  - [Table of contents](#table-of-contents)
  - [macOS installation](#macos-installation)
  - [Components](#components)
  - [Usage](#usage)
  - [Restarting machines](#restarting-machines)
  - [Links](#links)

## macOS installation

```bash
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python get-pip.py --user
python -m pip install --user ansible
python -m pip install --user paramiko
```

[↑ Installing Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).

## Components

- **Playbooks** — plain-text YAML files that describe the desired state of something. They are human and machine readable and can be used to build entire application environments.
- **Variables**
- **Inventories** — list of things you want to automate from. In order to run a task or an Ansible command we need a list of targets on which to automate.
- **Playbooks**. Playbooks contain **plays**. Plays contain **tasks**. Tasks call **modules**. Tasks run sequentially. **Handlers** are triggered by tasks, and are run once, at the end of plays.

## Usage

1\. If `/etc/ansible/hosts` file doesn't already exist, create it:

```bash
sudo mkdir /etc/ansible
sudo vim /etc/ansible/hosts
```

Example of `hosts` file contents:

```text
[nodes]
node1 ansible_ssh_host=node1.slova.io ansible_ssh_user=aleksei
node2 ansible_ssh_host=node2.slova.io ansible_ssh_user=aleksei

[masters]
master1 ansible_ssh_host=178.154.235.126 ansible_ssh_user=aleksei

[all:vars]
ansible_python_interpreter=/usr/bin/python3
```

The `all:vars` subgroup sets the `ansible_python_interpreter` host parameter that will be valid for all hosts included in this inventory. This parameter makes sure the remote server uses the `/usr/bin/python3` Python 3 executable instead of `/usr/bin/python` (Python 2.7), which is not present on recent Ubuntu versions.

Whenever you want to check your inventory, you can run:

```bash
ansible-inventory --list -y
```

Make sure that you have [↑ set up your ssh keys](https://stackoverflow.com/questions/2419566/best-way-to-use-multiple-ssh-private-keys-on-one-client) for different hosts propery.

2\. To check that everything works fine run Ansible's `ping` module:

```bash
ansible -m ping nodes
```

3\. Run [povisioning.yml](provisioning.yaml) playbook:

```bash
ansible-playbook -l nodes provisioning.yaml
```

## Restarting machines

See [reboot.yaml](reboot.yaml) file.

## Links

[↑ How to Install and Configure Ansible on Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-ansible-on-ubuntu-18-04).

[↑ Configuration Management 101: Writing Ansible Playbooks](https://www.digitalocean.com/community/tutorials/configuration-management-101-writing-ansible-playbooks).

[↑ Specifying SSH key in Ansible playbook file](https://stackoverflow.com/questions/44734179/specifying-ssh-key-in-ansible-playbook-file).
