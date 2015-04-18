Docker
======

[![Build Status](https://travis-ci.org/dirn/ansible-docker.svg?branch=master)](https://travis-ci.org/dirn/ansible-docker)

An Ansible role to install [Docker](https://www.docker.com/).

Requirements
------------

This role works on OS X and Debian-based OSes. If using OS X, make sure you have
[Homebrew](http://brew.sh/) and [Homebrew Cask](http://caskroom.io/) installed
before running the role. If you're looking for a role to handle them for you,
check out [dirn.homebrew](https://github.com/dirn/ansible-homebrew).

Role Variables
--------------

Several variables are available to configure the role.

To control where the related utilities are installed:

    docker_utility_root: /usr/local/bin

To control if and which version of [Machine](https://github.com/docker/machine)
is installed:

    docker_install_machine: false
    docker_version_machine: v0.2.0

> `docker_version_machine` isn't used in OS X since Homebrew is used to manage
> installation.

To control if [Compose](https://github.com/docker/compose) is installed:

    docker_install_compose: false
    docker_version_compose: '1.2.0'

> `docker_version_compose` isn't used in OS X since Homebrew is used to manage
> installation.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: dirn.docker
          docker_install_machine: true
          docker_install_compose: true

License
-------

MIT

Author Information
------------------

This role was created by [Andy Dirnberger](https://github.com/dirn).
