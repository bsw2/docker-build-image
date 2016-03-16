docker-build-image
============

[![Build Status](https://travis-ci.org/wangsha/docker-build-image.svg?branch=master)](https://travis-ci.org/wangsha/docker-build-image)
[![Ansible Galaxy](https://img.shields.io/badge/AnsibleGalaxy-wangsha.docker--build-image-blue.svg)](https://galaxy.ansible.com/wangsha/docker-build-image/)

Ansible role to manage and run the build-image docker container.

Requirements
------------

This role has only been tested on Ubuntu 14.04. Since this uses Ansible's
docker module, you will need to ensure that a recent-ish version of `docker-py`
and `docker` are installed.

Examples
--------

Install this module from Ansible Galaxy into the './roles' directory:
```bash
ansible-galaxy install wangsha.docker-build-image -p ./roles
```

Use it in a playbook as follows:
```yaml
- hosts: 'servers'
  roles:
    - role: wangsha.docker-build-image
      become: true
      app_source_repo: https://github.com/docker-library/hello-world.git
      app_source_version: master
      app_dockerfile_path: /
      app_name: hello-world

      docker_registry: https://index.docker.io/v1/
      docker_registry_login: yes
      docker_registry_username: your_dockerhub_username
      docker_registry_password: your_dockerhub_password
      docker_registry_email: your_dockerhub_email
```

Have a look at the [defaults/main.yml](defaults/main.yml) for role variables
that can be overridden.



Additional References
---------------------
- [docker private registry](http://rominirani.com/2015/07/27/docker-tutorial-series-part-6-docker-private-registry/)
- [docker hub](https://docs.docker.com/docker-hub/overview/)

License
-------

[MIT](LICENSE.txt)

Author Information
------------------

- wangsha
