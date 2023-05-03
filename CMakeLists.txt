# CMakeList.txt : CMake project for task_flow_bug, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)
include(FetchContent)

FetchContent_Declare(
  taskflow
  GIT_REPOSITORY https://github.com/taskflow/taskflow.git
  GIT_TAG        v3.5.0 # release-1.10.0
)
FetchContent_MakeAvailable(taskflow)
project ("task_flow_bug")

# Add source to this project's executable.
add_executable (task_flow_bug "task_flow_bug.cpp" "task_flow_bug.h")
target_link_libraries(task_flow_bug taskflow)

# TODO: Add tests and install targets if needed.
