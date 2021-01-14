### Packer builds for VMware vSphere (vsphere-iso)

This repository holds Packer builds declarations to create base virtual machines, with minimal installed packages and configurations.

Yo can clone or fork this repository to customize your own build configuration.

## Requisites

 The following software must be installed on your machine before you can build any of the virtual machine images

 * [Packer](https://www.packer.io)
 * [vSphere vCenter - _licensed_](https://my.vmware.com/en/web/vmware/downloads/info/slug/datacenter_cloud_infrastructure/vmware_vsphere/7_0)
 * [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

## Tested on

* VMware vSphere 6.7 Update 2
* Packer version: 1.6.6 (go1.15.6)
