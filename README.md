# chrony Setup

Role that setup the [rsyslog](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/system_administrators_guide/s1-basic_configuration_of_rsyslog) service, it also make sure that `logrotate` is setup and allows to tweak the number of open files used by `rsyslog`.

## Requirements

This role was created using [Ansible 2.9](https://docs.ansible.com/ansible/2.9/) for macOS and tested using the [centos/7](https://app.vagrantup.com/centos/boxes/7) boxes for [Vagrant v.2.2.6](https://www.vagrantup.com/docs/index.html) with [VirtualBox](https://www.virtualbox.org/) as a Provider.

The [Ansible modules](https://docs.ansible.com/ansible/2.9/modules/modules_by_category.html) used in the role are:

- [yum](https://docs.ansible.com/ansible/2.9/modules/yum_module.html#yum-module) - requires Python 2 and `yum` (for Python 3 see [dnf](https://docs.ansible.com/ansible/2.9/modules/dnf_module.html#dnf-module));
- [copy](https://docs.ansible.com/ansible/2.9/modules/copy_module.html#copy-module)
- [file](https://docs.ansible.com/ansible/2.9/modules/file_module.html#file-module)
- [template](https://docs.ansible.com/ansible/2.9/modules/template_module.html#template-module)
- [service](https://docs.ansible.com/ansible/2.9/modules/service_module.html#service-module)

## Role Variables

The only variable to be used is `rsyslog_nofile_limit` that setups the max number of open files used by `rsyslog`, defaults to `16384`.

## Dependencies

This role doesn't have any dependencies.

## Example Playbook

A working example using Vagrant and Virtual Box is setup under [tests](./tests/).
