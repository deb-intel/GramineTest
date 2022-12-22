.. _prerequisites

Prerequisites
-------------

Gramine without SGX support has no special requirements.

Gramine with SGX support has the following requirements:

- The FSGSBASE feature of recent processors must be enabled in the Linux kernel
- The Intel SGX driver must be built in the Linux kernel
- Intel SGX SDK/PSW and (optionally) Intel DCAP must be installed

If your system doesn't meet these requirements, please refer to the :doc:`devel/building` section for instructions on how to install these requirements.

Check for SGX compatibility
---------------

To check your hardware and system for SGX compatibility, use the supplied tool, :doc:`manpages/is-sgx-available`. It's installed together with the respective gramine
package you install from the options below.