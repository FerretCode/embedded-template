cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)

project(test_project C CXX ASM)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

pico_sdk_init()

add_executable(test test.cpp)

pico_enable_stdio_usb(test 1)
pico_enable_stdio_uart(test 1)

pico_add_extra_outputs(test)

target_link_libraries(test
    pico_stdlib
)

include_directories(
    ${PICO_SDK_PATH}/src/common/pico_stdlib/include
    ${PICO_SDK_PATH}/src/rp2_common/hardware_gpio/include
    ${PICO_SDK_PATH}/src/rp2_common/hardware_i2c/include
    ${PICO_SDK_PATH}/src/common/pico_base/include
)

target_include_directories(test PRIVATE ${PICO_SDK_PATH}/src/common)

