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

target_link_libraries(${PROJECT_NAME} PRIVATE
        arduino-variant
        esp32-sdk
        core-esp32
        )