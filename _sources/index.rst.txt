*********************
Gramine Documentation
*********************

Gramine is a lightweight guest OS that's designed to run a single Linux
application with minimal host requirements. Gramine can run applications in an
isolated environment with benefits comparable to running a complete OS in a
virtual machine, including guest customization, ease of porting to
different host OSs, and process migration.

Gramine supports running Linux applications using the Intel Software Guard Extensions, or Intel SGX. Refer to the :doc:`sgx-intro`.

.. list-table:: Get Started
   :widths: 25 25 25
   :header-rows: 1

   * - Install 
     - Contribute
     - Community
   * - :doc:`Installation-index`
     - :doc:`devel/contributing`
     - `Join user groups <https://groups.google.com/g/gramine-users>`__
   * - 5 available options
     - Thanks for your interest!
     - `Send questions <users@gramineproject.io>`__



.. toctree::
   :hidden:
   :caption: Getting Started 
   :maxdepth: 1

   Installation-index
   configuration-index
   tutorials-index
   concepts-index

.. toctree::  
   :hidden:
   :caption: Developer Reference
   :maxdepth: 1

   devel/packaging
   libos/libos-init
   devel/new-syscall
   pal/host-abi
   python/api

.. toctree::
   :hidden:
   :caption: Project Contribution
   :maxdepth: 1

   devel/onboarding
   devel/contributing
   gramine-users
   devel/DCO/index
   devel/howto-doc
   devel/coding-style
   devel/setup
   devel/debugging

.. toctree::
   :hidden:
   :caption: Glossary
   :maxdepth: 1

   glossary

.. toctree::
   :hidden:
   :caption: Index
   :maxdepth: 1

   :ref:`modindex`