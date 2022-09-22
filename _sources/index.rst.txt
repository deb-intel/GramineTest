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

+---------------------------------------------+
| :doc:`Installation-index <Install Gramine>` |        
+=============================================+



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
   :caption: Developer Guides
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
   :hidden:
   :caption: Glossary
   :maxdepth: 1

   glossary

.. toctree::
   :hidden:
   :caption: Index
   :maxdepth: 1

   :ref:`modindex`