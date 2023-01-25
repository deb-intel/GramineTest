.. _index_installation

Select a Deployment Option
==========================

Choose one of the deployment options based on your business need or preference.

Ready-Made Protected Applications
---------------------------
Images are ready-made for popular open source projects such as PyTorch and Redis. Customize your environment through Interactive scripts. The result is an image that includes your specific machine-learning application, common dependencies, and a manifest file. Note that these confidential compute images only run on machines that support Intel SGX.

**Select** :doc:`curated-installation`

Protect Your Container
--------------------------
This option is used when you have an application enclosed in a Docker container and you want the to protect the Docker container. This option converts your Docker container in to a graminized Docker container. A Gramine Shielded Container (GCS) supplies the Gramine Library OS, the manifest files, and any related Intel® SGX information.

**Select** :doc:`gsc-installation`

Protect Your Application
-------------------
In this section contains installation instructions for the supported versions of Ubuntu. This option enables you to take advantage of SGX without having to make modifications to an existing application. However, using this option requires you to manually create a manifest file. 

**Select** :doc:`custom-installation` to select the custom installation that best matches your use case.

