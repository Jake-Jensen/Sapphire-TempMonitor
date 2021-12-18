# Generated Cmake Pico project file

cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# initalize pico_sdk from installed location
# (note this can come from environment, CMake cache etc)
set(PICO_SDK_PATH "/home/sapphire/pico/pico-sdk")

# Pull in Raspberry Pi Pico SDK (must be before project)
include(pico_sdk_import.cmake)

project(Sapphire_TempMonitor C CXX ASM)

# Initialise the Raspberry Pi Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1

add_executable(Sapphire_TempMonitor Sapphire_TempMonitor.cpp )

pico_set_program_name(Sapphire_TempMonitor "Sapphire_TempMonitor")
pico_set_program_version(Sapphire_TempMonitor "0.1")

pico_enable_stdio_uart(Sapphire_TempMonitor 0)
pico_enable_stdio_usb(Sapphire_TempMonitor 1)

# Add the standard library to the build
target_link_libraries(Sapphire_TempMonitor pico_stdlib)

# Add any user requested libraries
target_link_libraries(Sapphire_TempMonitor
        hardware_i2c
        )

pico_add_extra_outputs(Sapphire_TempMonitor)

