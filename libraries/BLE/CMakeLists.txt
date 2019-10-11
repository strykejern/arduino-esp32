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