cmake_minimum_required(VERSION 3.4.1)

add_library(andcl SHARED
            ImageSobelFilter.cpp
            aopencl.c
            load.c)

target_include_directories(andcl PRIVATE
                          ${CMAKE_CURRENT_SOURCE_DIR}
                          )

# Include libraries needed for hello-jni lib
target_link_libraries(andcl
                      android
                      log)
