*********************
Gramine Documentation
*********************

Gramine is a lightweight guest OS that's designed to run a single Linux application with minimal host requirements. Gramine can run applications in an isolated environment with benefits comparable to running a complete OS in a virtual machine, including guest customization, ease of porting to different host OSs, and process migration.

Gramine supports running Linux applications using the Intel Software Guard Extensions, or Intel SGX. Refer to the :doc:`sgx-intro`.

Gramine Deployment Options
------------------------------------
There are three deployment options for Gramine- each option is described below. There is also one option to help develop Gramine.

Ready-made protected applications
=====================================
Images are ready-made for popular open source projects such as PyTorch and Redis. Customize your environment through interactive scripts. The result is an image that includes your specific machine-learning application, common dependencies, and a manifest file. Note that these confidential compute images only run on machines that support Intel SGX.

:doc:`curated-installation`

Protect your container
============================
This option is used when you have an application enclosed in a Docker container and you want the to protect the Docker container. This option converts your Docker container in to a graminized Docker container otherwise known as Gramine Shielded Container (GCS). A Gramine Shielded GCS supplies the Gramine Library OS, the manifest files, and any related Intel® SGX information.

:doc:`gsc-installation`

Protect your application
==========================
This section contains :doc:`quickstart`. It explains how to install Gramine on several different version so Ubuntu. It provides instructions on how to :doc:`enviornment-setup` and :doc:`run-sample-aaplicaiton`. 

 plains how to install Gramine from binaries. In this section you find instructions on how to  requires you to install Gramine from binaries, setting up your environment to run Gramine, preparing a signing key to ensure your applications are protected, and instructions for running sample applications to test your environment. This option enables you to take advantage of SGX without having to make modifications to an existing application. However, using this option requires you to manually create a manifest file. 

:doc:`custom-installation`

Develop Gramine
===================================

This section describes how to develop Gramine. It contains instructions to :doc:`devel/building`` which includes preparing signing keys. It also includes instructions for :doc:`devel/debugging`.  , and if needed, installing a Linux kernel with FSBSBASE patches. 

:doc:`devel/building`

If you would like to contribute to the Gramine project, follow the link below. We welcome your involvement and appreciate new ideas. The link below provides information on how to go about contributing to Gramine. 

:doc:`devel/contributor-index`

Resources
===============
The Gramine project provides resources to help you understand and develop it. The resources page contains a list of maintainers, users, and a glossary to help you with any questions you may have. 

:doc:`management-team`

Indices and tables
==================

- :ref:`genindex`
- :ref:`search`

.. toctree::
   :hidden:
   :caption: Ready Made Protected Applications 
   :maxdepth: 1

   curated-installation

.. toctree::
   :hidden:
   :caption: Protect your container 
   :maxdepth: 1

   gsc-installation


.. toctree::
   :hidden:
   :caption: Protect your application
   :maxdepth: 1

   quickstart
   environment-setup
   run-sample-application
   configuration-index
   tutorials-index


.. toctree::
   :hidden:
   :caption: Develop Gramine 
   :maxdepth: 1

   devel/building
   devel/debugging
   devel/new-syscall
   pal/host-abi
   python/api
   concepts-index
   contributor-index

.. toctree::
   :hidden:
   :caption: Resource
   :maxdepth: 0

   management-team
   gramine-users
   glossary

