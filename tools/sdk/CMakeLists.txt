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

project(esp32-sdk)

add_library(${PROJECT_NAME} INTERFACE)

target_include_directories(${PROJECT_NAME} INTERFACE
        include/app_trace
        include/app_update
        include/asio
        include/bootloader_support
        include/bt
        include/coap
        include/config
        include/console
        include/driver
        include/esp32
        include/esp32-camera
        include/esp_adc_cal
        include/esp_event
        include/esp-face
        include/esp_http_client
        include/esp_http_server
        include/esp_https_ota
        include/esp_ringbuf
        include/esp-tls
        include/ethernet
        include/expat
        include/fatfs
        include/fb_gfx
        include/freemodbus
        include/freertos
        include/heap
        include/idf_test
        include/jsmn
        include/json
        include/libsodium
        include/log
        include/lwip
        include/mbedtls
        include/mdns
        include/micro-ecc
        include/mqtt
        include/newlib
        include/nghttp
        include/nvs_flash
        include/openssl
        include/protobuf-c
        include/protocomm
        include/pthread
        include/sdmmc
        include/smartconfig_ack
        include/soc
        include/spiffs
        include/spi_flash
        include/tcpip_adapter
        include/tcp_transport
        include/ulp
        include/vfs
        include/wear_levelling
        include/wifi_provisioning
        include/wpa_supplicant
        include/xtensa-debug-module
        )

target_link_directories(${PROJECT_NAME} INTERFACE
        lib/
        )

target_link_libraries(${PROJECT_NAME} INTERFACE
        app_trace
        app_update
        asio
        bootloader_support
        bt
        btdm_app
        c
        c_nano
        coap
        coexist
        console
        core
        stdc++
        dl_lib
        driver
        esp32
        esp32-camera
        esp_adc_cal
        esp_event
        esp_http_client
        esp_http_server
        esp_https_ota
        espnow
        esp_ringbuf
        esp-tls
        ethernet
        expat
        face_detection
        face_recognition
        fatfs
        fb_gfx
        fd
        fr
        freemodbus
        freertos
        hal
        heap
        image_util
        jsmn
        json
        libsodium
        log
        lwip
        m
        mbedtls
        mdns
        mesh
        micro-ecc
        mqtt
        net80211
        newlib
        nghttp
        nvs_flash
        openssl
        phy
        pp
        protobuf-c
        protocomm
        pthread
        rtc
        sdmmc
        smartconfig
        smartconfig_ack
        soc
        spiffs
        spi_flash
        tcpip_adapter
        tcp_transport
        ulp
        vfs
        wear_levelling
        wifi_provisioning
        wpa2
        wpa
        wpa_supplicant
        wps
        xtensa-debug-module
        )