cmake_minimum_required(VERSION 3.22)

project(words-drop)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_BUILD_TYPE "Release")
add_compile_options(-Os -O3)

find_package(Qt5 REQUIRED COMPONENTS Widgets)
find_package(yaml-cpp REQUIRED)
find_package(creeper-qt REQUIRED)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

add_executable(${PROJECT_NAME}
    main.cc
    window.cc
)
target_link_libraries(${PROJECT_NAME}
    creeper-qt::creeper-qt
    Qt5::Widgets yaml-cpp
)
