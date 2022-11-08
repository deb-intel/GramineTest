.. _custom_installation

Quick Install or Custom Build Gramine
=====================================

Install Gramine and all components on your own server. Select this option if you have an existing application and you want to take advantage of SGX without making modifications. You must create your own manifest. 

**Select** Use :doc:`quickstart` instructions to quickly install and run Gramine. For full build instructions, see :doc:`devel/building`.

.. toctree::
   :maxdepth: 1

   quickstart
   devel/building

If you opt to custom-build Gramine, you can install Gramine from a Docker container you build that includes an OS packaged with Gramine binaries. The container includes everything that's included in the custom installation. You must create your own manifest.

**Select** :doc:`docker-image-installation`

Gramine can be installed in the cloud on VMs that support Intel SGX.

**Select** :doc:`cloud-deployment`

Refer to the following as you configure and develop Gramine.
   
- :doc:`configuration-index`
- :doc:`developer-index`
- :doc:`tutorials-index`
- :doc:`concepts-index`