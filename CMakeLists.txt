# BSD 3-Clause License
#
# Copyright (c) 2019, Anders B. Eie
# All rights reserved.
#
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions are met:
#
# 1. Redistributions of source code must retain the above copyright notice, this
# list of conditions and the following disclaimer.
#
# 2. Redistributions in binary form must reproduce the above copyright notice,
# this list of conditions and the following disclaimer in the documentation
# and/or other materials provided with the distribution.
#
# 3. Neither the name of the copyright holder nor the names of its
# contributors may be used to endorse or promote products derived from
# this software without specific prior written permission.
#
# THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
# AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
# IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
# DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
# FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
# DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
# SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
# CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
# OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
# OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

project(arduino-esp32)

add_subdirectory(cores)
add_subdirectory(libraries)
add_subdirectory(tools/sdk)

set(COMPONENT_SRCS ${CORE_SRCS} ${LIBRARY_SRCS} ${AZURE_SRCS} ${BLE_SRCS})

set(COMPONENT_ADD_INCLUDEDIRS
  variants/esp32/
  )

set(COMPONENT_PRIV_INCLUDEDIRS cores/esp32/libb64)

set(COMPONENT_REQUIRES spi_flash mbedtls mdns ethernet)
set(COMPONENT_PRIV_REQUIRES fatfs nvs_flash app_update spiffs bootloader_support openssl bt)

set_source_files_properties(libraries/AzureIoT/src/az_iot/iothub_client/src/iothubtransport_mqtt_common.c
    PROPERTIES COMPILE_FLAGS
    -Wno-maybe-uninitialized
)

# Arduino variant target to be "linked" by all libraries

add_library(arduino-variant INTERFACE)

target_include_directories(arduino-variant INTERFACE
        variants/esp32/
        )

target_compile_options(arduino-variant INTERFACE
        -std=gnu++11
        -fno-exceptions
        -Os
        -g3
        -Wpointer-arith
        -fexceptions
        -fstack-protector
        -ffunction-sections
        -fdata-sections
        -fstrict-volatile-bitfields
        -mlongcalls
        -nostdlib
        -w
        -Wno-error=unused-function
        -Wno-error=unused-but-set-variable
        -Wno-error=unused-variable
        -Wno-error=deprecated-declarations
        -Wno-unused-parameter
        -Wno-sign-compare
        -fno-rtti
        )