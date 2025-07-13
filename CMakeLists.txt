cmake_minimum_required(VERSION 3.27)

# initialize pico-sdk from submodule
include(external/pico-sdk/pico_sdk_init.cmake)

project(limpo-watch)

# initialize the Raspberry Pi Pico SDK
pico_sdk_init()

file(GLOB_RECURSE SRC src/*.c)

add_executable(${PROJECT_NAME} main.c ${SRC})
target_link_libraries(${PROJECT_NAME} pico_stdlib lvgl::lvgl)

# create map/bin/hex/uf2 file etc.
pico_add_extra_outputs(${PROJECT_NAME})

set(CONFIG_LV_BUILD_EXAMPLES OFF)
set(CONFIG_LV_BUILD_DEMOS OFF)
add_subdirectory(external/lvgl)