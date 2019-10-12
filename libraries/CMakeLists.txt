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

project(arduino-libraries)

add_subdirectory(BLE/)
#add_subdirectory(AzureIoT/)

add_library(${PROJECT_NAME} STATIC)

target_sources(${PROJECT_NAME} PRIVATE
        ArduinoOTA/src/ArduinoOTA.cpp
        AsyncUDP/src/AsyncUDP.cpp
        BluetoothSerial/src/BluetoothSerial.cpp
        DNSServer/src/DNSServer.cpp
        EEPROM/src/EEPROM.cpp
        ESPmDNS/src/ESPmDNS.cpp
        FFat/src/FFat.cpp
        FS/src/FS.cpp
        FS/src/vfs_api.cpp
        HTTPClient/src/HTTPClient.cpp
        HTTPUpdate/src/HTTPUpdate.cpp
        NetBIOS/src/NetBIOS.cpp
        Preferences/src/Preferences.cpp
        SD_MMC/src/SD_MMC.cpp
        SD/src/SD.cpp
        SD/src/sd_diskio.cpp
        SD/src/sd_diskio_crc.c
        SimpleBLE/src/SimpleBLE.cpp
        SPIFFS/src/SPIFFS.cpp
        SPI/src/SPI.cpp
        Ticker/src/Ticker.cpp
        Update/src/Updater.cpp
        WebServer/src/WebServer.cpp
        WebServer/src/Parsing.cpp
        WebServer/src/detail/mimetable.cpp
        WiFiClientSecure/src/ssl_client.cpp
        WiFiClientSecure/src/WiFiClientSecure.cpp
        WiFi/src/ETH.cpp
        WiFi/src/WiFiAP.cpp
        WiFi/src/WiFiClient.cpp
        WiFi/src/WiFi.cpp
        WiFi/src/WiFiGeneric.cpp
        WiFi/src/WiFiMulti.cpp
        WiFi/src/WiFiScan.cpp
        WiFi/src/WiFiServer.cpp
        WiFi/src/WiFiSTA.cpp
        WiFi/src/WiFiUdp.cpp
        Wire/src/Wire.cpp
        )

target_include_directories(${PROJECT_NAME} PUBLIC
        ArduinoOTA/src
        AsyncUDP/src
        BluetoothSerial/src
        DNSServer/src
        EEPROM/src
        ESP32/src
        ESPmDNS/src
        FFat/src
        FS/src
        HTTPClient/src
        HTTPUpdate/src
        NetBIOS/src
        Preferences/src
        SD_MMC/src
        SD/src
        SimpleBLE/src
        SPIFFS/src
        SPI/src
        Ticker/src
        Update/src
        WebServer/src
        WiFiClientSecure/src
        WiFi/src
        Wire/src
        )

target_link_libraries(${PROJECT_NAME} PUBLIC
        arduino-variant
        core-esp32
        )