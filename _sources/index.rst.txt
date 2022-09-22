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

.. raw:: html

<div  class="vc_col-sm-8 wpb_column column_container vc_column_container col centered-text no-extra-padding inherit_tablet inherit_phone "  data-padding-pos="all" data-has-bg-color="false" data-bg-color="" data-bg-opacity="1" data-animation="" data-delay="0" >
      <div class="vc_column-inner" >
         <div class="wpb_wrapper">
            <h2 style="text-align: center" class="vc_custom_heading" >A Big Little Hypervisor for IoT Development</h2><div class="divider-wrap" data-alignment="default"><div style="height: 35px;" class="divider"></div></div><h4 style="text-align: left" class="vc_custom_heading" >ACRN™ is a flexible, lightweight reference hypervisor, built with real-time and safety-criticality in mind, optimized to streamline embedded development through an open source platform</h4><div class="divider-wrap" data-alignment="default"><div style="height: 35px;" class="divider"></div></div><a class="nectar-button large see-through-2 "  style="margin-right: 30px; border-color: #ffffff; color: #ffffff;"  href="https://github.com/projectacrn/acrn-hypervisor" data-color-override="#ffffff"  data-hover-color-override="#067480" data-hover-text-color-override="#ffffff"><span>Download from GitHub</span></a><a class="nectar-button large see-through-2 "  style="border-color: #ffffff; color: #ffffff;"  href="https://projectacrn.github.io/latest/index.html" data-color-override="#ffffff"  data-hover-color-override="#067480" data-hover-text-color-override="#ffffff"><span>Read Documentation</span></a>
         </div> 

      **Install Gramine**
      ^^^^^^^^^^^^^^^^^^^
      :ref:`index_installation`

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