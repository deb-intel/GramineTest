.. _quickstart_installation

Install Gramine from binaries
===========

These instructions describe how to install Gramine from binaries. If you prefer to work with source file, go to :doc:`devel/building`.

.. highlight:: sh

Prerequisites
-------------

Gramine without SGX support has no special requirements.

Gramine with SGX support has the following requirements:

- The FSGSBASE feature of recent processors must be enabled in the Linux kernel
- The Intel SGX driver must be built in the Linux kernel
- Intel SGX SDK/PSW and (optionally) Intel DCAP must be installed

If your system doesn't meet these requirements, please refer to the :doc:`devel/building` section for instruction on how to install these requirements.

Check for SGX compatibility
---------------

To check your hardware and system for SGX compatibility, use the supplied tool, :doc:`manpages/is-sgx-available`. It's installed together with the respective gramine
package you install from the options below.

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


Prepare a signing key
---------------------

These instructions are only required for systems using SGX and have not already created a signing key.

   - If your system is not using SGX, skip to Run the sample application.

   - If your system is using SGX and you already created a signing key, skip to Run the sample application. 

   - If your system is using SGX and have not created a signing key, follow the instructions below. 

The following command generates an |~| RSA 3072 key suitable for signing SGX enclaves
and stores it in :file:`{HOME}/.config/gramine/enclave-key.pem`. Protect
this key and do not disclose it to anyone:: 

   gramine-sgx-gen-private-key


glibc vs musl
-------------

Most of the examples we provide use GNU C Library (glibc). If your application
is built against musl libc, you can pass ``'musl'`` to
:py:func:`gramine.runtimedir()` when generating the manifest from a template;
this will mount musl libc (instead of the default glibc).
