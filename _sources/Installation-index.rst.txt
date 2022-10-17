.. _index_installation

Deploy Gramine
==============

Choose one of the deployment options based on your business need or preference.

Intel Confidential Compute images with Gramine
----------------------------------------------
Images are ready-made for popular machine-learning apps such as PyTorch and Redis. Customize your environment through Interactive scripts. The result is an image that includes your specific machine-learning application, common dependencies, and a manifest file. Note that these confidential Compute images only run on machines that support Intel SGX.

**Select** :doc:`curated-installation`

Gramine Shielded Container
--------------------------
Bring an application as a Docker container and then your container is transformed into a "graminized" Docker container.

**Select** :doc:`gsc-installation`

Custom installation
-------------------
Install Gramine and all components on your own server. Select this option is you have an existing application and you want to take advantage of SGX without making modifications. You must create your own manifest. 

**Select** Use :doc:`quickstart` instructions to quickly install and run Gramine. For full build instructions, see :doc:`devel/building`.





