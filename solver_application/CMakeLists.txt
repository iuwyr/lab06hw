cmake_minimum_required(VERSION 3.10)
project(solver_app)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(solver equation.cpp)

target_link_libraries(solver PUBLIC solver_lib formatter_ex)