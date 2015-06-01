Trainings
=========

A playbook for setting up instances and users for a training session.

Requirements
------------

The [files/userlist](files/userlist) file contains a list of usernames to be added as accounts to the control machine. One username per line.

OpenStack ansible modules required:

 - `novaclient`
 - `neutronclient`
 - `keystoneclient`

Minimum Ansible version `1.8`.

Role Variables
--------------

The following are mandatory variables that must be set in order for the playbooks to work:

- In [host_vars/localhost.yml](host_vars/localhost.yml):

  - `os_auth_url` - The OpenStack authentication endpoint URL.
  - `os_key_name` - The OpenStack name identification of the SSH key to inject on the control machine.
  - `os_username` - An OpenStack username with access to the `training` tenant.
  - `os_password` - The password matching the user above.

Example Playbook
----------------

To set up the environment, run the [training-setup.yml](training-setup.yml) playbook:

```
$ ansible-playbook -i "localhost," training-setup.yml
```
