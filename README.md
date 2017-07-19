[![Build Status](https://travis-ci.org/CSCfi/ansible-role-cuda.svg)](https://travis-ci.org/CSCfi/ansible-role-cuda)
[![Galaxy Role](https://img.shields.io/badge/ansible--galaxy-cuda-blue.svg)](https://galaxy.ansible.com/CSCfi/cuda/)

ansible-role-cuda
=========

Installs CUDA

Tested with Tesla P100, K80, Tesla M40, CentOS7, Ubuntu 16.04, Cuda 7.5 and 8.0

Optionally also installs cuda_init which initializes the GPUs during boot.

Requirements
------------

Outbound access to http://developer.download.nvidia.com/compute/cuda/repos/

Role Variables
--------------

    gpu: False
    cuda_packages:
     - cuda
    cuda_restart_node_on_install: True
    cuda_init: True
    cuda_bash_profile: True

- gpu: True is needed. Without it this role does nothing.
- cuda_packages: List that can be updated to include more packages that are installed after nvidia cuda repo is installed, or to a specific cuda package (e.g. `cuda-7-5`)
- cuda_init: Installs a bash script that is executed via systemd
- cuda_gpu_name0: "/dev/nvidia0" # set this to the device ansible looks for. If it does not exist then if cuda_init is True then it will run the cuda_init.sh script
- cuda_restart_node_on_install: restarts the system when packages are installed or updated


Example Playbook
----------------

`playbook.yml`:

    - hosts: deep_learning
      roles:
        - CSC-IT-Center-for-Science.cuda

`inventory`:

    [deep_learning]
    host1.example gpu=True

Example Errors
--------------

This error means you are not using a supported OS (like Ubuntu 17.04 which does not have a cuda URL)
<pre>
   "msg": "No file was found when using with_first_found. Use the 'skip: true' option to allow this task to be skipped if no files are found"
</pre>

License
-------

MIT

Author Information
------------------

