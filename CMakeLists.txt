cmake_minimum_required(VERSION 3.16)
project(grf C)

set(CMAKE_C_STANDARD 99)

include_directories(include)

find_package(ZLIB REQUIRED)
include_directories(ZLIB_INCLUDE_DIRS)

find_package(ICONV REQUIRED)

set(GRF_SRC src/grf.c src/grfcrypt.c src/grfsupport.c src/rgz.c)

add_library(grf SHARED ${GRF_SRC})

target_link_libraries(grf ${ZLIB_LIBRARIES} iconv)
