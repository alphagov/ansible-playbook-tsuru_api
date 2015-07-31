Tsuru API server
=========

An ansible role to install a [Tsuru API](https://tsuru.readthedocs.org/en/latest/) server.

Requirements
------------

Only tested on Ubuntu 14.04.

Role Variables
--------------

* `api_port` - Port upon which you wish to run the API server
* `healing_active_monitoring_interval` - Number of seconds between calls to `<server>/_ping` in each one of the docker nodes, [for more information check here](http://tsuru.readthedocs.org/en/stable/reference/config.html?highlight=unit#docker-healing-active-monitoring-interval)
* `healing_heal_containers_timeout` - Number of seconds a container should be unresponsive before triggering the recreation of the container, [for more information check here](http://tsuru.readthedocs.org/en/stable/reference/config.html?highlight=unit#docker-healing-heal-containers-timeout)
* `tsuru_api_internal_lb` - The hostname of the loadbalancer you wish to run tsuru behind.
* `mongodb_host` - MongoDB hostname
* `mongodb_port` - MongoDB server portnumber
* ` gandalf_host_external` - External hostname of the Gandalf server
* ` gandalf_port ` - The port number upon which you wish to run Gandalf
* ` gandalf_host_internal ` - The internal hostname of the Gandalf server.
* `hipache_host_external_lb` - The external Hipache hostname for loadbalancer.
* `redis_host` - The redis hostname.
* `redis_port` - The redis port.
* ` docker_registry_host ` - The Docker registry hostname.
* ` docker_registry_port ` - The Docker registry port.
* `tsuru_server_version` - The version of the tsuru server package to be installed
* `tsuru_client_version` - The version of the tsuru client package to be installed
* `tsuru_admin_version` - The version of the tsuru admin package to be installed
* `tsuru_package_latest` - Install the latest version of all packages, note this is mutually exclusive with options, `tsuru_server_version`, `tsuru_client_version` and `tsuru_admin_version`
* `tsuru_repo` repo argument for Ansible's [`apt_repository`](http://docs.ansible.com/ansible/apt_repository_module.html) module, defaults to `ppa:tsuru/ppa`


Dependencies
------------

* None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

- hosts: tsuru-api
  roles:
    - role: tsuru_api


License
-------

See `LICENSE` file.
