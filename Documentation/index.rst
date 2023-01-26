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

**Select** :doc:`curated-installation`

Protect your container
============================
This option is used when you have an application enclosed in a Docker container and you want the to protect the Docker container. This option converts your Docker container in to a graminized Docker container otherwise known as Gramine Shielded Container (GCS). A Gramine Shielded GCS supplies the Gramine Library OS, the manifest files, and any related Intel® SGX information.

**Select** :doc:`gsc-installation`

Protect your application
==========================
This option requires you to install Gramine from binaries, setting up your environment to run Gramine, preparing a signing key to ensure your applications are protected, and instructions for running sample applications to test your environment. This option enables you to take advantage of SGX without having to make modifications to an existing application. However, using this option requires you to manually create a manifest file. 

**Select** :doc:`custom-installation` to select the custom installation that best matches your use case.

Develop Gramine
-----------------
This section contains information on how to assist in developing Gramine. It contains instructions for building Gramine from source files, installing dependencies, debugging, preparing signing keys, and information on the contribution guidelines for Gramine.

**Select** :doc:`dev/building`

Indices and tables
==================

- :ref:`genindex`
- :ref:`modindex`
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
   environnment-setup
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
   :maxdepth: 1

   management-team
   gramine-users
   glossary

