cmdline
=========

Initial provisioning of a command line.
Installs and configures essential packages and tools.

Tested on the following distributions:
 * Debian buster
 * Debian 9
 * Ubuntu 16.04
 * Ubuntu 14.04

At the time of this writing, Ubuntu bionic doesn't support (this installation method of) docker yet.
If you don't plan on using this functionality, there is a good chance everything will work fine.

Requirements
------------

Tested on Ansible 2.5 or higher.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

Following packages will be installed

    cmdline_packages:
      - systemd
      - vim
      - tree
      - curl
      - python2.7
      - python3

Install ansible?

    cmdline_ansible_install: yes

Install docker? Note: an external role `geerlingguy.docker` will be used.

    cmdline_docker_install: no

There are more variables in `vars/main.yml`.
Change these only if you know what you're doing.

Dependencies
------------

Role: geerlingguy.docker

Make sure to check the variables for his role.
Especially `docker_users`.

Example Playbook
----------------

    - name: Cmdline provisioning
      hosts: all
      tasks:
        - import_role:
            name: cmdline

 License
 -------

 MIT / BSD

 Author Information
 ------------------

 jniewt | [jniewt@gmail.com](jniewt@gmail.com)
