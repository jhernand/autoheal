# Auto-heal Service Installation Ansible Role

This directory contains the Ansible role used to install the auto-heal service.

## Installation

The role uses the following variables:

- `openshift_autoheal_deploy`: `true` - install/update. `false` - uninstall.
  Defaults to `true`.

- `openshift_autoheal_namespace`: Namespace where the components will be
  deployed. Defaults to `openshift-autoheal`.

- `openshift_autoheal_name`: Prefix for the names for the objects that compose
  the the auto-heal service. Defaults to `autoheal`.

- `openshift_autoheal_awx_address`: The URL of the Ansible Tower or AWX server
  that will run the auto-heal playbooks. For example `https://myawx.example.com/api`.
  This variable is mandatory when `openshift_autoheal_deploy` is `true`, it doesn't
  have a default value.

- `openshift_autoheal_awx_proxy`: The URL of the proxy that should be used to
  connect to the Ansible Tower or AWX server. For example
  `http://myproxy.example.com:3128`. Defaults to no proxy.

- `openshift_autoheal_awx_user`: The name of the Ansible Tower or AWX user.
  Defaults to `autoheal`.

- `openshift_autoheal_awx_password`: The password of the Ansible Tower or AWX user.
  This variable is mandatory when `openshift_autoheal_deploy` is `true`, it doesn't
  have a default value.

- `openshift_autoheal_awx_ca`: PEM encoded CA certificates that will be used to
  verify the certificate presented by the Ansible Tower or AWX server. Defaults
  to the CA certificates of the machine.

- `openshift_autoheal_awx_project`: The name of the Ansible Tower or AWX project
  that contains the aut-heal job templates. Defaults to `Auto-heal`.

For example, to install the auto-heal service so that it talks to the AWX server
in `myawx.example.com', add these variables to your inventory file:

```ini
openshift_autoheal_awx_address="https://myawx.example.com/api"
openshift_autoheal_awx_user="myuser"
openshift_autoheal_awx_password="mypassword"
openshift_autoheal_awx_project="My project"
```
