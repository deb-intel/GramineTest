.. _custom_installation

Custom Install, Configure, Develop
==================================

Install Gramine and all components on your own server. Select this option is you have an existing application and you want to take advantage of SGX without making modifications. You must create your own manifest. 

**Select** Use :doc:`quickstart` instructions to quickly install and run Gramine. For full build instructions, see :doc:`devel/building`.

You can also install Gramine from a Docker container you build that includes an OS packaged with Gramine binaries. The container includes everything that's included in the custom installation. You must create your own manifest.

**Select** :doc:`docker-image-installation`

Gramine can be installed in the cloud on VMs that support Intel SGX.

**Select** :doc:`cloud-deployment`

Refer to the following as you configure and develop Gramine.

.. toctree::  
   :maxdepth: 1
   
   configuration-index
   developer-index
   tutorials-index
   concepts-index
   contributor-index