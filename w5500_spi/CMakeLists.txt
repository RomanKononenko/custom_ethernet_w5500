cmake_minimum_required(VERSION 3.13)
include(pico_sdk_import.cmake)
project(test_project C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
pico_sdk_init()
add_executable(w5500_spi
        w5500_spi.c
        loopback.c socket.c w5500.c wizchip_conf.c
        )

#add_library(loopback.c socket.c w5500.c wizchip_conf.c)
# Pull in our (to be renamed) simple get you started dependencies
target_link_libraries(w5500_spi pico_stdlib hardware_spi) 
target_include_directories(w5500_spi PRIVATE ${CMAKE_CURRENT_LIST_DIR} )

# create map/bin/hex file etc.
pico_add_extra_outputs(w5500_spi)
pico_enable_stdio_usb(w5500_spi 1)
pico_enable_stdio_uart(w5500_spi 0)

# add url via pico_set_program_url
#example_auto_set_url(w5500_spi)
