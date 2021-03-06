# Ansible Role: Jenkins CI

Installs Jenkins CI on RHEL/CentOS 6.x servers.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `vars/main.yml`):

    hostname: localhost

The system hostname; usually `localhost` works fine. This will be used during setup to communicate with the running Jenkins instance via HTTP requests.

    jenkins_jar_location: /opt/jenkins-cli.jar

The location at which the `jenkins-cli.jar` jarfile will be kept. This is used for communicating with Jenkins via the CLI.

    jenkins_plugins:
      - git
      - sonar
      - ssh

Jenkins plugins to be installed automatically during provisioning. You can always install more plugins via the Jenkins UI at a later time, but this is helpful in getting things up and running more quickly.

## Dependencies

  - geerlingguy.java

## Example Playbook

    - hosts: ci-server
      vars_files:
        - vars/main.yml
      roles:
        - { role: geerlingguy.jenkins }

*Inside `vars/main.yml`*:

    hostname: jenkins-example.com

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
