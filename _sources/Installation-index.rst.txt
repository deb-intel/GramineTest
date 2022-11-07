.. _index_installation

Select a Deployment Option
==========================

Choose one of the deployment options based on your business need or preference.

Confidential Compute images
---------------------------
Images are ready-made for popular open source projects such as PyTorch and Redis. Customize your environment through Interactive scripts. The result is an image that includes your specific machine-learning application, common dependencies, and a manifest file. Note that these confidential compute images only run on machines that support Intel SGX.

**Select** :doc:`curated-installation`

Gramine Shielded Container
--------------------------
Bring an application as a Docker container and then your container is transformed into a "graminized" Docker container.

**Select** :doc:`gsc-installation`

Custom installation
-------------------
Install Gramine and all components on your own server. Select this option if you have an existing application and you want to take advantage of SGX without making modifications. You must create your own manifest. 

**Select** Use :doc:`custom-installation` to select the custom installation that best matches your use case.





