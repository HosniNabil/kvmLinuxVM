kvmLinuxVM
=========
Ansible role to provision a Linux virtual machine on a KVM host

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------
- vm_hostname: virtual machine template name
- vm_cpu: number of CPU of the virtual machine
- vm_memory: memory in MB of the virtual machine
- vm_network: KVM network to chose
- vm_ip: VM IP address
- vm_prefix: VM IP prefix
- vm_gw: VM primary network card gateway
- vm_dns: VM DNS IP address
- rhel_7_path: RHEL 7 cloud image path in the KVM HOST
- rhel_8_path: RHEL 8 cloud image path in the KVM HOST
- centos_7_path: CentOS 7 cloud image url to download from
- centos_8_path: CentOS 8 cloud image url to download from
- ubuntu_18_path: Ubuntu 18 cloud image url to download from
- ubuntu_20_path: Ubuntu 20 cloud image url to download from
- vm_root_password: VM root password
- vm_user: Default User to create
- vm_authorized_ssh: Public ssh key to copy to the VM

Example Playbook
----------------
    - hosts: KVMHost
      roles:
         - role:
              name: hosninabil.kvmLinuxVM
           vars:
              dist: "centos"
              version: "8"
              vm_cpu: 1
              vm_memory: 2048
              vm_network: default
              vm_user: nabil
              vm_ip: 10.112.42.106
              vm_prefix: 24
              vm_gw: 10.112.42.254
              vm_dns: 8.8.8.8

License
-------
Apache License 2.0

Author Information
------------------
Nabil Hosni, cloud engineer and opensource enthusiast.
