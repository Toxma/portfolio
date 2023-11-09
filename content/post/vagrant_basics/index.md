---
title: "Introduction Vagrant"
description: Les bases à savoir pour commencer à utiliser Vagrant
date: 2023-11-10T11:17:22Z
image: vagrant.png
slug: vagrant-basics
hidden: false
comments: true
draft: true
categories:
    - Vagrant
---

## Liens utiles

- [Vagrant Documentation](https://developer.hashicorp.com/vagrant/docs)

---

## Environment

- [VSCode extension for syntax](https://marketplace.visualstudio.com/items?itemName=marcostazi.VS-code-vagrantfile)

### QEMU/KVM + Libvirt

- Install vagrant

```bash
 wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
 echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
 sudo apt update && sudo apt install vagrant
```

- Install Qemu/KVM + libvirt

```bash
sudo apt install qemu-kvm,libvirt-daemon-system,ksmtuned,libvirt-clients,libxslt-dev,libxml2-dev,libvirt-dev,zlib1g-dev,ruby-dev,ruby-libvirt,ebtables
sudo usermod -aG libvirt $USER
```

- Install Vagrant plugin for libvirt

```bash
vagrant plugin install vagrant-libvirt
```

---

## Basics

### Download image

```bash
vagrant box add os/version

list | remove | update
```

- [Vagrant Boxes](https://app.vagrantup.com/boxes/search)

### Create conf file

```bash
vagrant init os/version

-m : minimal vagrant file
```

- Create Vagrantfile for the box

### Provisionning

```bash
vagrant up

--no-destroy-on-error   : keep vm even if error
--provision             : Force provision 
```

- Launch provisionning with VagrantFile
- Create .vagrant
- [Docs CLI](https://developer.hashicorp.com/vagrant/docs/cli/up)

### Connect to VM

```bash
vagrant ssh
```

- Connect with SSH to the VM

```bash
vagrant ssh-config 
```

- Show details about ssh

### Reload VM

```bash
vagrant reload

--provision : Force provision 
```

- reload = halt + up

### Suspend / Resume VM

```bash
vagrand suspend
vagrand resume
```

- suspend : save state / not fully shutdown

### Shutdown

```bash
vagrant halt

-f : force
```

- correctly shut down
- if -f just shut off power

### Destroy

```bash
vagrant destroy

-f : force / no confirmation
```

- Destroy VM

---

## Vagrantfile

- [Documentation Vagrantfile](https://developer.hashicorp.com/vagrant/docs/vagrantfile)

### Conventions

- \# or /**/ to comment
- key = value
- string : ""
- bool : true or false

### Validation

```bash
vagrant validate
```

- output the state of vagrantfile