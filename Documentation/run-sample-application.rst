.. _run_sample_application

Run sample application
=======================
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