cmake_minimum_required(VERSION 2.6)
project(ogg)

set ( CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -ffast-math -fsigned-char")

if(${ANDROID_ABI} STREQUAL "armeabi")
    set ( CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -march=armv6 -marm -mfloat-abi=softfp -mfpu=vfp")
endif()

include_directories( ${CMAKE_CURRENT_SOURCE_DIR}/include )
file( GLOB SRC "${CMAKE_CURRENT_SOURCE_DIR}/src/*.c" )

add_library( ogg STATIC ${SRC} )
