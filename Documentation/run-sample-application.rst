.. _run_sample_application


Run a sample application
=======================



Prerequisites
---------------------------

Gramine without SGX has no special requirements.

Gramine with SGX support requires several features from your system:

- The FSGSBASE feature of recent processors must be enabled in the Linux kernel;

- The Intel SGX driver must be built in the Linux kernel;

- Intel SGX SDK/PSW and (optionally) Intel DCAP must be installed.

If your system doesn’t meet these requirements, please refer to more detailed descriptions in Custom-Build Gramine.

Check for SGX compatibility
-----------------------------------

We supply a tool, <a href=""https://deb-intel.github.io/GramineTest/manpages/is-sgx-available.html>is-sgx-available – Check environment for SGX compatibility</a>, which you can use to check your hardware and system. It’s installed together with the respective gramine package you install from the options below.

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


Prepare a signing key  
---------------------------------------------

Only for SGX, and if you haven’t already, enter the following:

.. parsed-literal::

gramine-sgx-gen-private-key


This command generates an RSA 3072 key suitable for signing SGX enclaves and stores it in HOME/.config/gramine/enclave-key.pem. Protect this key and do not disclose it to anyone.


Run a sample application
=======================
The core Gramine repository contains several sample application to
test the Gramine installation, clone the Gramine repo:

.. parsed-literal::

   git clone --depth 1 |stable-checkout| \https://github.com/gramineproject/gramine.git


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
------------------------------------
Most of the examples we provide use GNU C Library (glibc). If your application is built against musl libc, you can pass ''musl'' to ''gramine.runtimedir()'' when generating the manifest from a template; this will mount musl libc (instead of the default glibc).