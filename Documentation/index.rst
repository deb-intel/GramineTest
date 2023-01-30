*********************
Gramine Documentation
*********************

Gramine is a lightweight guest OS that's designed to run a single Linux application with minimal host requirements. Gramine can run applications in an isolated environment with benefits comparable to running a complete OS in a virtual machine, including guest customization, ease of porting to different host OSs, and process migration.

Gramine supports running Linux applications using the Intel Software Guard Extensions, or Intel SGX. For mor information, refer to the :doc:`sgx-intro`article.

Gramine Deployment Options
------------------------------------
There are three deployment options for Gramine- each option is described below. There is also one option to help develop Gramine.

Ready-made protected applications
=====================================
Confidential compute images are ready-made solutions for popular open source projects such as `PyTorch <https://github.com/gramineproject/contrib/tree/master/Curated-Apps/workloads/pytorch>`_ and `Redis <https://github.com/gramineproject/contrib/tree/master/Curated-Apps/workloads/redis>`_. These images enable you to customize your environment through interactive scripts. The result is an image that includes your specific machine-learning application, common dependencies, and a manifest file. 

>[!NOTE] 
>Note that these confidential compute images only run on machines that support Intel SGX.

:doc:`curated-installation`

Protect your container
============================
Docker images are used to run applications in the cloud. The Gramine Shielded Container tool transforms a Docker image into a graminized image that includes the Gramine Library OS, and Intel SGX related information. It enables you to run a an application an Docker image and keep it protected. 

- :doc:`gsc-installation` - Get an overview of the installation process of a Gramine Shielded Container.
-  `Build a Gramine Docker image <https://gramine.readthedocs.io/projects/gsc/en/latest/>`_ - Run a graminized Docker image. 
-  `Download the Gramine Shielded Container tool <https://github.com/gramineproject/gsc>`_ - 


Protect your application
==========================

If you have an existing application you would like to protect with Gramine, this is the option to implement. Little to no addition modification of your application is needed. To protect your application with Gramine, these are the processes to follow:

- :doc:`Install Gramine<devel/building>` - Install Gramine from binaries on to the various supported versions of Ubuntu or install a Docker image with Gramine included. 
- :doc:`Set up the environment<environment-setup>` - Set up the Gramine environment to work with or without SGX and prepare a signing key.
- :doc:`Run a sample application` - Run a sample application to ensure your environment is running correctly. 
- :doc:`Configure` - Configuring Gramine involves creating a manifest file, setting up attestation, and performance tuning.


Develop Gramine
===================================

This section describes how to develop Gramine. It contains instructions to:

- :doc:`Build Gramine from Source files<Install Gramine<devel/building>` - Build Gramine and ensure all the dependencies installed with proper drivers. This option requires a more work but allows you to chose build options. 
- :doc:`Set up Debugging<devel/debugging>` - Configure Gramine with Gnu Debugger (GDB) and setup compiling optimizations.
- :doc:`Implement a new system call<new0syscall>` - Define the interface of the system call, add, import, and Implement new PAL calls if needed. 

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

