cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)

project(OCircuit)

pico_sdk_init()

add_executable(OCircuit)

pico_generate_pio_header(OCircuit ${CMAKE_CURRENT_LIST_DIR}/hello.pio)

target_sources(OCircuit PRIVATE OCircuit.c)

# Pull in our (to be renamed) simple get you started dependencies
target_link_libraries(OCircuit PRIVATE pico_stdlib pico_multicore hardware_irq hardware_i2c hardware_pwm hardware_pio hardware_dma hardware_spi )

pico_enable_stdio_usb(OCircuit 0)
pico_enable_stdio_uart(OCircuit 0)

# create map/bin/hex file etc.
pico_add_extra_outputs(OCircuit)