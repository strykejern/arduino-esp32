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

project(esp32-BLE)

add_library(${PROJECT_NAME} STATIC)

target_sources(${PROJECT_NAME} PRIVATE
        src/BLE2902.cpp
        src/BLE2904.cpp
        src/BLEAddress.cpp
        src/BLEAdvertisedDevice.cpp
        src/BLEAdvertising.cpp
        src/BLEBeacon.cpp
        src/BLECharacteristic.cpp
        src/BLECharacteristicMap.cpp
        src/BLEClient.cpp
        src/BLEDescriptor.cpp
        src/BLEDescriptorMap.cpp
        src/BLEDevice.cpp
        src/BLEEddystoneTLM.cpp
        src/BLEEddystoneURL.cpp
        src/BLEExceptions.cpp
        src/BLEHIDDevice.cpp
        src/BLERemoteCharacteristic.cpp
        src/BLERemoteDescriptor.cpp
        src/BLERemoteService.cpp
        src/BLEScan.cpp
        src/BLESecurity.cpp
        src/BLEServer.cpp
        src/BLEService.cpp
        src/BLEServiceMap.cpp
        src/BLEUtils.cpp
        src/BLEUUID.cpp
        src/BLEValue.cpp
        src/FreeRTOS.cpp
        src/GeneralUtils.cpp
        )

target_include_directories(${PROJECT_NAME} PUBLIC
        src/
        )

target_link_libraries(${PROJECT_NAME} PRIVATE
        arduino-variant
        esp32-sdk
        core-esp32
        )