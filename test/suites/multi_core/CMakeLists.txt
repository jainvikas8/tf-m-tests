#-------------------------------------------------------------------------------
# Copyright (c) 2020, Arm Limited. All rights reserved.
#
# SPDX-License-Identifier: BSD-3-Clause
#
#-------------------------------------------------------------------------------

cmake_policy(SET CMP0079 NEW)

if (NOT TFM_MULTI_CORE_TOPOLOGY)
    return()
endif()

add_library(tfm_test_suite_multi_core_ns STATIC EXCLUDE_FROM_ALL)

#CMSIS
include_directories(${TFM_TEST_REPO_PATH}/CMSIS/RTOS2/Include ABSOLUTE)

target_sources(tfm_test_suite_multi_core_ns
    PRIVATE
        non_secure/multi_core_ns_interface_testsuite.c
)

target_include_directories(tfm_test_suite_multi_core_ns
    PUBLIC
        non_secure
)

target_compile_definitions(tfm_test_suite_multi_core_ns
    PRIVATE
        DOMAIN_NS=1
)

target_link_libraries(tfm_test_suite_multi_core_ns
    PRIVATE
        tfm_test_framework
        psa_api_ns
)

target_link_libraries(tfm_ns_tests
    INTERFACE
        tfm_test_suite_multi_core_ns
)

target_compile_definitions(psa_interface
    INTERFACE
        TFM_MULTI_CORE_TEST
)
