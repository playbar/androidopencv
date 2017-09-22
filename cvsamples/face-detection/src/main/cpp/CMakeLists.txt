cmake_minimum_required(VERSION 3.4.1)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=gnu++11 -fPIC  -shared -Wno-error -frtti -fexceptions -Wno-format-security")

add_library(detection_tracker SHARED
            DetectionBasedTracker_jni.cpp
            load.c)

target_include_directories(detection_tracker PRIVATE
                          ${CMAKE_CURRENT_SOURCE_DIR}
                          ${CMAKE_CURRENT_SOURCE_DIR}/../../../../sdk/src/main/cpp/include)


add_library(lib_opencv SHARED IMPORTED )
set_target_properties(lib_opencv PROPERTIES IMPORTED_LOCATION
        ${CMAKE_SOURCE_DIR}/../../../../sdk/src/main/jniLibs/${ANDROID_ABI}/libopencv_java3.so)

# Include libraries needed for hello-jni lib
target_link_libraries(detection_tracker
                      android
                      lib_opencv
                      log)
