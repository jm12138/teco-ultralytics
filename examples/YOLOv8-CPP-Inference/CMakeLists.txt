cmake_minimum_required(VERSION 3.5)

project(Yolov8CPPInference VERSION 0.1)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

# SDAA
set(SDAA_TOOLKIT_ROOT_DIR "/usr/local/sdaa")
find_package(SDAA 11 REQUIRED)

set(CMAKE_SDAA_STANDARD 11)
set(CMAKE_SDAA_STANDARD_REQUIRED ON)
# !SDAA

# OpenCV
find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})
# !OpenCV

set(PROJECT_SOURCES
    main.cpp

    inference.h
    inference.cpp
)

add_executable(Yolov8CPPInference ${PROJECT_SOURCES})
target_link_libraries(Yolov8CPPInference ${OpenCV_LIBS})
