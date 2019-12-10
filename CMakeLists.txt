cmake_minimum_required (VERSION 3.5)

project (track_targets)

find_package(wpilib REQUIRED)
find_package(OpenCV REQUIRED)

include_directories(${OpenCV_INCLUDE_DIRS})

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY /home/nvidia/robot_programs)

add_definitions(-std=c++14)

aux_source_directory(src CV_SOURCES)

add_executable(cv_track_targets ${CV_SOURCES})

target_link_libraries(cv_track_targets ${OpenCV_LIBS} cscore ntcore wpiutil)
    

