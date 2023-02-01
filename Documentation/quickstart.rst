.. _quickstart_installation

Gramine installation options
----------------------------

There are three options to choose from when using Gramine to protect your application. The option you choose depends on how you are running your application. installing Gramine. These option are listed below.. The option you choose depends on how you are running your application. 

:ref:`Install Gramine on your system <Install Gramine>` - This option provides instructions for installing Gramine on various version of Ubuntu or Red Hat Enterprise Linux 8.  

:ref:`Gramine Docker Image` - This option provides instructions for installing a prepared Docker image with Gramine and running the container. This option enables you to protect an application running in the cloud. 

Another option to installing Gramine is to build it from source files. This option is much more involved. The instructions for this option are listed on another page.

:doc:`devel/building` - This option is also used to help develop Gramine.  

Install Gramine 
================

On Ubuntu 22.04 and Debian 11::

   sudo curl -fsSLo /usr/share/keyrings/gramine-keyring.gpg https://packages.gramineproject.io/gramine-keyring.gpg
   echo 'deb [arch=amd64 signed-by=/usr/share/keyrings/gramine-keyring.gpg] https://packages.gramineproject.io/ stable main' | sudo tee /etc/apt/sources.list.d/gramine.list

   curl -fsSL https://download.01.org/intel-sgx/sgx_repo/ubuntu/intel-sgx-deb.key | sudo apt-key add -
   echo 'deb [arch=amd64] https://download.01.org/intel-sgx/sgx_repo/ubuntu focal main' | sudo tee /etc/apt/sources.list.d/intel-sgx.list

   sudo apt-get update

   sudo apt-get install gramine      # for 5.11+ upstream, in-kernel driver
   sudo apt-get install gramine-oot  # for out-of-tree SDK driver
   sudo apt-get install gramine-dcap # for out-of-tree DCAP driver


On Ubuntu 20.04::

   sudo curl -fsSLo /usr/share/keyrings/gramine-keyring.gpg https://packages.gramineproject.io/gramine-keyring.gpg
   echo 'deb [arch=amd64 signed-by=/usr/share/keyrings/gramine-keyring.gpg] https://packages.gramineproject.io/ focal main' | sudo tee /etc/apt/sources.list.d/gramine.list

   curl -fsSL https://download.01.org/intel-sgx/sgx_repo/ubuntu/intel-sgx-deb.key | sudo apt-key add -
   echo 'deb [arch=amd64] https://download.01.org/intel-sgx/sgx_repo/ubuntu focal main' | sudo tee /etc/apt/sources.list.d/intel-sgx.list

   sudo apt-get update

   sudo apt-get install gramine      # for 5.11+ upstream, in-kernel driver
   sudo apt-get install gramine-oot  # for out-of-tree SDK driver
   sudo apt-get install gramine-dcap # for out-of-tree DCAP driver


On Ubuntu 18.04::

   sudo curl -fsSLo /usr/share/keyrings/gramine-keyring.gpg https://packages.gramineproject.io/gramine-keyring.gpg
   echo 'deb [arch=amd64 signed-by=/usr/share/keyrings/gramine-keyring.gpg] https://packages.gramineproject.io/ bionic main' | sudo tee /etc/apt/sources.list.d/gramine.list

   curl -fsSL https://download.01.org/intel-sgx/sgx_repo/ubuntu/intel-sgx-deb.key | sudo apt-key add -
   echo 'deb [arch=amd64] https://download.01.org/intel-sgx/sgx_repo/ubuntu bionic main' | sudo tee /etc/apt/sources.list.d/intel-sgx.list

   sudo apt-get update

   sudo apt-get install gramine      # for 5.11+ upstream, in-kernel driver
   sudo apt-get install gramine-oot  # for out-of-tree SDK driver
   sudo apt-get install gramine-dcap # for out-of-tree DCAP driver


Install Gramine on RHEL-8-like distributions (like AlmaLinux 8, CentOS 8, Rocky Linux 8, ...):: 

   sudo curl -fsSLo /etc/yum.repos.d/gramine.repo https://packages.gramineproject.io/rpm/gramine.repo
   sudo dnf install gramine          # only the default, distro-provided kernel is supported

Gramine Docker image
========================

This Gramine image is a minimal distribution of Gramine. It contains only Gramine binaries and tools, as well as the pre-requisite packages to run applications under Gramine. The only currently available Gramine image is based on Ubuntu 20.04. The only requirement on the host system is a Linux kernel with in-kernel SGX driver (available from version 5.11 onward). This Gramine image can be used as a disposable playground environment, to quickly test Gramine with your applications and workloads. This image can also be used as a base for your workflows to produce production-ready Docker images for your SGX applications. 

The Gramine team publishes a base Gramine Docker image at `DockerHub <https://hub.docker.com/r/gramineproject/gramine>`_.

The recommended command to run the Gramine image via Docker is::

    docker run --device /dev/sgx_enclave -it gramineproject/gramine

If you want to run :program:`gramine-direct` in addition to
command:`gramine-sgx`, then you should run Docker with our custom seccomp
profile using:

 ``--security-opt seccomp=<profile_file>``. 

You can download the profile file from:

https://github.com/gramineproject/gramine/blob/master/scripts/docker_seccomp.json.

Alternatively you can disable seccomp completely using this command:

(``--security-optseccomp=unconfined``).