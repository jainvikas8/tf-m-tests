########################
Trusted Firmware-M Tests
########################

The Trusted Firmware-M(TF-M) Tests repo is meant to hold various tests for the
`Trusted Firmware-M`_.
The TF-M tests mainly focus on functionalities of various TF-M componentes such
as the TF-M core and various secure partitions.

There is also the `psa-arch-tests`_ suite which mainly focuses on the
implementation compliance of the Platform Security Architecture(PSA).

##################################
Mbed OS + Trusted Firmware-M Tests
##################################

This specific branch supports additional patches required for integration
of Mbed OS with Trusted Firmware-M tests latest implementation.

.. Note::
    This branch is experimental and not to be used for any production
    purpose, the Mbed OS patches should be tested and reviewed again
    before upstreaming.

****************
Folder Structure
****************

- app - The application code that executes the testing, including both the TF-M
  tests and the `psa-arch-tests`_.
- CMSIS - The libraries of RTX which is the Non-secure RTOS of the tests
- test - The TF-M test codes including test framework, test suites and test
  services


####################
Feedback and support
####################
Feedback can be submitted via email to
`TF-M mailing list <tf-m@lists.trustedfirmware.org>`__.

.. _Trusted Firmware-M: https://git.trustedfirmware.org/TF-M/trusted-firmware-m.git/
.. _psa-arch-tests: https://github.com/ARM-software/psa-arch-tests

*Copyright (c) 2020, Arm Limited. All rights reserved.*
