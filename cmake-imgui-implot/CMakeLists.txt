# CMakeList.txt : CMake project for cmake-imgui-implot, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

project ("cmake-imgui-implot")

# Add source to this project's executable.
add_executable (cmake-imgui-implot "cmake-imgui-implot.cpp" "cmake-imgui-implot.h")

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET cmake-imgui-implot PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.

add_subdirectory(lib)

target_link_libraries(cmake-imgui-implot PUBLIC imgui)
target_link_libraries(cmake-imgui-implot PUBLIC implot)

