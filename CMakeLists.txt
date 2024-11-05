cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)

project(pico_apds9960_project C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
pico_sdk_init()

add_library(pico_apds9960 src/pico_apds9960.cpp)

target_include_directories(pico_apds9960 PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)
target_include_directories(pico_apds9960 PRIVATE ${CMAKE_CURRENT_LIST_DIR}/src)

target_link_libraries(pico_apds9960
  pico_stdlib
  hardware_i2c
)
