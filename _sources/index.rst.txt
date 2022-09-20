***********************
Introduction to Gramine
***********************

Gramine is a |~| lightweight guest OS, designed to run a |~| single Linux
application with minimal host requirements. Gramine can run applications in an
isolated environment with benefits comparable to running a |~| complete OS in a
|~| virtual machine -- including guest customization, ease of porting to
different host OSes, and process migration.

Gramine supports running Linux applications using the :term:`Intel SGX <SGX>`
(Software Guard Extensions) technology (we sometimes call this version
**Gramine-SGX**).  With Intel SGX, applications are secured in
hardware-encrypted memory regions (called SGX enclaves). SGX protects code and
data in the enclave against privileged software attacks and against physical
attacks on the hardware off the CPU package (e.g., cold-boot attacks on RAM).
Gramine is able to run unmodified applications inside SGX enclaves, without the
toll of manually porting the application to the SGX environment.

Gramine Installation Options
Install everything on your own. 

Install using a container.

Install using command line arguments.

Install using a curated GSC.



External documentation
======================

This website contains the official documentation of Gramine. For external
contributions and additional resources, please visit
https://gramine-contrib.readthedocs.io. Note that this link contains unofficial
documents; these documents are not guaranteed to always be up-to-date and
correct.


GSC documentation
=================

For GSC (Gramine Shielded Containers) documentation please visit
https://gramine.readthedocs.io/projects/gsc.

Building and running Gramine
============================

See :doc:`quickstart` for instructions how to quickly install and run Gramine.
For full build instructions, see :doc:`devel/building`. To deploy Gramine in the
cloud, see :doc:`cloud-deployment`.

Contacts and Contributing
=========================

For bug reports, post an issue on our GitHub repository:
https://github.com/gramineproject/gramine/issues.

For any questions, please send an email to users@gramineproject.io
(`public archive <https://groups.google.com/g/gramine-users>`__).

If you want to contribute to the project, please see :doc:`devel/contributing`
and :doc:`devel/onboarding`. Thank you for your interest!

*****************
Table of Contents
*****************

.. toctree::
   :caption: Installation 
   :maxdepth: 2

   quickstart
   docker-image-installation
   gsc-installation
   curated-installation
   cloud-deployment

.. toctree::
   :caption: Configuration 
   :maxdepth: 2

   manifest-syntax
   attestation
   performance
   manpages/index.rst

.. toctree::
   :caption: SGX Concepts
   :maxdepth: 1

   sgx-intro

.. toctree::
   :caption: Tutorials
   :maxdepth: 2

   tutorials/pytorch/index.rst
   tutorials/cczoo/index.rst

.. toctree::
   :caption: Developer Guides
   :maxdepth: 2

   devel/packaging
   libos/libos-init
   devel/new-syscall
   pal/host-abi
   python/api

.. toctree::
   :caption: Project Contribution
   :maxdepth: 2

   devel/building
   devel/onboarding
   devel/contributing
   gramine-users
   devel/DCO/index
   devel/howto-doc
   devel/coding-style
   devel/setup
   devel/debugging

.. toctree::
   :caption: Glossary
   :maxdepth: 1

   glossary

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
