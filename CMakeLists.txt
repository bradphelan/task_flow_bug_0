# CMakeList.txt : CMake project for task_flow_bug, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)
include(FetchContent)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

FetchContent_Declare(
  taskflow
  GIT_REPOSITORY https://github.com/taskflow/taskflow.git
  GIT_TAG        v3.5.0 # release-1.10.0
)
FetchContent_MakeAvailable(taskflow)
project ("task_flow_bug")

# Add source to this project's executable.
add_executable (task_flow_bug "task_flow_bug.cpp" "task_flow_bug.h")
message(STATUS ${CMAKE_BINARY_DIR})
target_include_directories(task_flow_bug PRIVATE ${CMAKE_BINARY_DIR}/_deps/taskflow-src)

