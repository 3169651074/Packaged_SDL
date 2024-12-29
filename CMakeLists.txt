cmake_minimum_required(VERSION 3.30)
set(EXECUTABLE_NAME "C-Test")
project(${EXECUTABLE_NAME} LANGUAGES C)

set(CMAKE_C_STANDARD 23)
set(EXECUTABLE_OUTPUT_PATH "${CMAKE_SOURCE_DIR}/bin")
set(LIBRARY_OUTPUT_PATH ${EXECUTABLE_OUTPUT_PATH})

include_directories("${CMAKE_SOURCE_DIR}/include")
link_directories("${CMAKE_SOURCE_DIR}/lib")

file(GLOB_RECURSE SOURCES "${CMAKE_SOURCE_DIR}/src/*.c")
add_executable(${EXECUTABLE_NAME} ${SOURCES})

target_link_libraries(${EXECUTABLE_NAME} PUBLIC
        mingw32 SDL2 SDL2main SDL2_image SDL2_mixer SDL2_net SDL2_ttf)

#SDL Library Updated 20241225