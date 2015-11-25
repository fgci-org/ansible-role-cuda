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
cuda_packages:
 - "cuda"
</pre>

This list can be updated to include more packages that are installed after nvidia cuda repo is installed.


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

