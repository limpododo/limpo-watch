cmake_minimum_required(VERSION 3.27)

# initialize pico-sdk from submodule
include(sdk/pico-sdk/pico_sdk_init.cmake)

project(limpo-watch)

# initialize the Raspberry Pi Pico SDK
pico_sdk_init()

add_executable(${PROJECT_NAME} main.c)
target_link_libraries(${PROJECT_NAME} pico_stdlib)

# create map/bin/hex/uf2 file etc.
pico_add_extra_outputs(${PROJECT_NAME})
