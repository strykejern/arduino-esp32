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

target_link_libraries(${PROJECT_NAME} PUBLIC
        arduino-variant
        esp32-sdk
        )