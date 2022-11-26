cmake_minimum_required(VERSION 3.10)
project(Rasterizer)

find_package(OpenCV REQUIRED)

set(CMAKE_CXX_STANDARD 17)

include_directories(/usr/local/include)

# Mac OS eigen path
IF(CMAKE_SYSTEM_NAME MATCHES "Darwin")
    include_directories(/opt/homebrew/Cellar/eigen/3.4.0_1/include/)
ENDIF (CMAKE_SYSTEM_NAME MATCHES "Darwin")

add_executable(Rasterizer main.cpp rasterizer.hpp rasterizer.cpp global.hpp Triangle.hpp Triangle.cpp)
target_link_libraries(Rasterizer ${OpenCV_LIBRARIES})
