[![Build Status](https://travis-ci.org/CSC-IT-Center-for-Science/ansible-role-cuda.svg)](https://travis-ci.org/CSC-IT-Center-for-Science/ansible-role-cuda)
ansible-role-cuda
=========

Installs CUDA

Tested with Tesla K80 and CentOS7

Requirements
------------

http://developer.download.nvidia.com/compute/cuda/repos/

Role Variables
--------------

<pre>
gpu: True
cuda_packages:
 - "cuda"
</pre>

- gpu: True is needed. Without it this role does nothing.
- cuda_packages: List that can be updated to include more packages that are installed after nvidia cuda repo is installed.
- cuda_init: Installs a bash script that is executed via rc.local on boot




Dependencies
------------


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: ansible-role-cuda }

In the hosts file have

<pre>
[servers]
host1.example.com gpu=True
</pre>


License
-------

MIT

Author Information
------------------

