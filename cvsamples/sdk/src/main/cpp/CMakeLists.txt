cmake_minimum_required(VERSION 3.4.1)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=gnu++11 -fPIC  -shared -Wno-error, -fexceptions, -Wno-format-security")

#add_library(sdk SHARED  )

# Include libraries needed for hello-jni lib
#target_link_libraries(sdk android log GLESv2)
