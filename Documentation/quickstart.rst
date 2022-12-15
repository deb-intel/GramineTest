.. _quickstart_installation

Install Gramine on Ubuntu
===========

These instructions describe how to install Gramine on an Ubuntu operating system. 

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

Install Gramine on Ubuntu 18.04 or 20.04
---------------
Use the following commands to install Gramine on Ubuntu.

.. Note::
On Ubuntu 18.04, in :file:`intel-sgx.list`, replace
``focal`` with ``bionic``), run the following::

   sudo curl -fsSLo /usr/share/keyrings/gramine-keyring.gpg https://packages.gramineproject.io/gramine-keyring.gpg
   echo 'deb [arch=amd64 signed-by=/usr/share/keyrings/gramine-keyring.gpg] https://packages.gramineproject.io/ stable main' | sudo tee /etc/apt/sources.list.d/gramine.list

   curl -fsSL https://download.01.org/intel-sgx/sgx_repo/ubuntu/intel-sgx-deb.key | sudo apt-key add -
   echo 'deb [arch=amd64] https://download.01.org/intel-sgx/sgx_repo/ubuntu focal main' | sudo tee /etc/apt/sources.list.d/intel-sgx.list
   # (if you're on Ubuntu 18.04, remember to write "bionic" instead of "focal")

Select **one** of the three options below. You will get pre-packaged gramine binaries from an Ubuntu repo::

   sudo apt-get update

   sudo apt-get install gramine      # for 5.11+ upstream, in-kernel driver
   sudo apt-get install gramine-oot  # for out-of-tree SDK driver
   sudo apt-get install gramine-dcap # for out-of-tree DCAP driver

On **RHEL-8-like distributions** (like AlmaLinux 8, CentOS 8, Rocky Linux 8, ...) run the following::

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


Run the sample application
--------------------------

The core Gramine repository contains several sample application to
test the Gramine installation, clone the Gramine repo:

.. parsed-literal::

   git clone --depth 1 |stable-checkout| \https://github.com/gramineproject/gramine.git

Don't build Gramine as it is already installed on the system. Instead,
build and run the HelloWorld example. To build the HelloWorld application,
access the ``gcc`` compiler and the ``make`` build system by entering the
following::

   sudo apt-get install gcc make  # for Ubuntu distribution
   sudo dnf install gcc make      # for RHEL-8-like distribution

Go to the HelloWorld example directory::

   cd gramine/CI-Examples/helloworld

Build and run without SGX::

   make
   gramine-direct helloworld

Build and run with SGX::

   make SGX=1
   gramine-sgx helloworld

Other sample applications
-------------------------

Several applications that demonstrate Gramine usability are available in the :file:`CI-Examples` directory in the repository. Each application contains a
short README file with instructions how to test it. We recommend starting
with a simpler, thoroughly documented example of Redis to
understand manifest options and Gramine features.

Additional sample configurations for applications enabled in Gramine are
available in a separate repository https://github.com/gramineproject/examples.

Note that these sample applications are tested on Ubuntu 18.04 and 20.04.
Most of these applications run correctly on 
Fedora/RHEL/CentOS, but with caveats. One caveat is that Makefiles should be
invoked with ``ARCH_LIBDIR=/lib64 make``. Another caveat is that applications
that rely on specific versions/builds of Glibc may break (our GCC example is
known to work only on Ubuntu).

glibc vs musl
-------------

Most of the examples we provide use GNU C Library (glibc). If your application
is built against musl libc, you can pass ``'musl'`` to
:py:func:`gramine.runtimedir()` when generating the manifest from a template;
this will mount musl libc (instead of the default glibc).
