cmake_minimum_required(VERSION 3.16)

project(cw3 VERSION 1.0.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(Qt6 REQUIRED COMPONENTS Core Widgets)
qt_standard_project_setup()

qt_add_executable(quaketool
    src/main.cpp
    src/backend/dataset.cpp
    src/frontend/window.cpp
    src/frontend/file_select_widget.cpp
    src/backend/water_sample.cpp
)

target_include_directories(quaketool PRIVATE
  src
  src/frontend
  src/backend
)

target_link_libraries(quaketool PRIVATE Qt6::Widgets Qt6::Core)

set_target_properties(quaketool PROPERTIES
    WIN32_EXECUTABLE ON
    MACOSX_BUNDLE OFF
)
