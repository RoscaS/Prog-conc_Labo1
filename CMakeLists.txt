cmake_minimum_required(VERSION 3.12)
project(P_CONC_LABO1 C)

set(CMAKE_C_STANDARD 11 pthread)
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -pthread")

include_directories(/usr/include/)
link_directories(/usr/include/)

add_executable(P_CONC_LABO1 main.c)

find_package(Threads)
