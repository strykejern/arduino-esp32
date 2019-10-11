project(core-esp32)

add_library(${PROJECT_NAME} STATIC)

target_sources(${PROJECT_NAME} PRIVATE
        esp32/base64.cpp
        esp32/cbuf.cpp
        esp32/esp32-hal-adc.c
        esp32/esp32-hal-bt.c
        esp32/esp32-hal-cpu.c
        esp32/esp32-hal-dac.c
        esp32/esp32-hal-gpio.c
        esp32/esp32-hal-i2c.c
        esp32/esp32-hal-ledc.c
        esp32/esp32-hal-matrix.c
        esp32/esp32-hal-misc.c
        esp32/esp32-hal-psram.c
        esp32/esp32-hal-sigmadelta.c
        esp32/esp32-hal-spi.c
        esp32/esp32-hal-time.c
        esp32/esp32-hal-timer.c
        esp32/esp32-hal-touch.c
        esp32/esp32-hal-uart.c
        esp32/esp32-hal-rmt.c
        esp32/Esp.cpp
        esp32/FunctionalInterrupt.cpp
        esp32/HardwareSerial.cpp
        esp32/IPAddress.cpp
        esp32/IPv6Address.cpp
        esp32/libb64/cdecode.c
        esp32/libb64/cencode.c
        esp32/main.cpp
        esp32/MD5Builder.cpp
        esp32/Print.cpp
        esp32/stdlib_noniso.c
        esp32/Stream.cpp
        esp32/StreamString.cpp
        esp32/wiring_pulse.c
        esp32/wiring_shift.c
        esp32/WMath.cpp
        esp32/WString.cpp
        )

target_include_directories(${PROJECT_NAME} PUBLIC
        esp32/
        )

target_link_libraries(${PROJECT_NAME} PRIVATE
        arduino-variant
        esp32-sdk
        )