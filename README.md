# Bedrock
Open-source tools for WordPress application development.

## Requirements
At a minimum you need to have:

1. [Node.js](https://nodejs.org/en/download/) >= 0.12.x
2. [Gulp](https://github.com/gulpjs/gulp/blob/master/docs/getting-started.md) >= 3.8.10
3. [Bower](https://bower.io/#install-bower) >= 1.3.12

## Local development setup - Instructions based on Mac OSX

1 - Open the terminal and create your own directory.
```
cd ~/Desktop && mkdir bedrock && cd $_
```

2 - Clone roots.io repository
```
git init
git clone https://github.com/roots/roots-example-project.com.git
```

3 - Install Ansible

###### The preferred way to install ansible on a Mac is via pip.
```
sudo easy_install pip
sudo pip install ansible
```

###### Problems while installing?

  [Ansible Docs](http://docs.ansible.com/ansible/intro_installation.html#latest-releases-on-mac-osx) ||
  [Stackoverflow](http://stackoverflow.com/questions/17271319/installing-pip-on-mac-os-x)

4 - Install Virtualbox => [Download](https://www.virtualbox.org/wiki/Downloads)

5 - Install Vagrant => [Download](https://www.vagrantup.com/downloads.html)

**Latest Vagrant version (at the moment 1.8.4) may cause some problems, if so try to install previous ones [Old Releases](https://releases.hashicorp.com/vagrant/)**

6 - Install [vagrant-bindfs](https://github.com/gael-ian/vagrant-bindfs)

#####Vagrant-bindfs is distributed as a Ruby gem. You can install it as any other Vagrant plugin with:
```
vagrant plugin install vagrant-bindfs
```

7 - Install [vagrant-hostmanager](https://github.com/devopsgroup-io/vagrant-hostmanager)

```
vagrant plugin install vagrant-hostmanager
```

8 - Install external Ansible roles/packages

```
cd roots-example-project.com/trellis
ansible-galaxy install -r requirements.yml
```

9 - Install theme components

```
cd roots-example-project.com/site/web/app/themes/sage
npm install
bower install
gulp
```

10 - Fire up the server

```
cd roots-example-project.com/trellis
vagrant up
```
##### Note: to shut down the server:

```
vagrant halt
```

11 - Finally open your browser at [roots-example-project.dev](http://roots-example-project.dev)
