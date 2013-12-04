cmake_minimum_required(VERSION 2.8)

project(hexgame)

set(CXX_WARNING_FLAGS "-Wall -Wno-format-extra-args -Wformat-security -Wdelete-non-virtual-dtor -Wformat-nonliteral -Wformat=2 -Wpointer-arith -Wcast-align -Wshadow -Wsign-compare -Wno-variadic-macros -Wno-pmf-conversions")

set(CMAKE_CXX_FLAGS "-fvisibility=hidden -fno-rtti -pipe -std=gnu++11 ${CXX_WARNING_FLAGS}")
set(CMAKE_CXX_FLAGS_DEBUG    "-O0 -ggdb3")
set(CMAKE_CXX_FLAGS_RELEASE  "-Ofast -march=native -mtune=native -ggdb3 -DNDEBUG")

set(CMAKE_EXE_LINKER_FLAGS "-Wl,--as-needed -Wl,--hash-style=gnu")

include_directories(include)

add_executable(hex
  src/main.cpp
  )