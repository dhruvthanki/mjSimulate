cmake_minimum_required(VERSION 3.13)
project(Simulate)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -pthread")

set(MJC /home/dhruv/.local/lib/python3.8/site-packages/mujoco)
message("Mujoco Path : " ${MJC})
include_directories( ${MJC}/include )

find_package(glfw3 REQUIRED)

file(GLOB SRC_FILES ${PROJECT_SOURCE_DIR}/src/*.cc)
add_executable(mjSim ${SRC_FILES})

target_include_directories(mjSim PUBLIC 
    ${PROJECT_SOURCE_DIR}/include)

target_link_libraries(mjSim PUBLIC
    ${MJC}/libmujoco.so.2.3.0
    libglfw.so.3
    ${CMAKE_DL_LIBS})