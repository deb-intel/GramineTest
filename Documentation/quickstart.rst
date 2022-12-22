.. _quickstart_installation

Install Gramine from binaries
===========

These instructions describe how to install Gramine from binaries. If you prefer to work with source files, go to :doc:`devel/building`.

.. highlight:: sh

Install Gramine  
---------------

On Ubuntu 22.04 adn Debian 11::

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
