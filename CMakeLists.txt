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