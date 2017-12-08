project(myQt5Test)
cmake_minimum_required(VERSION 3.0.2)

find_package(Qt5 REQUIRED
    Widgets
)

include(${CMAKE_SOURCE_DIR}/qt_cmake_plugin/QtCommon.cmake REQUIRED)

# fix_project_version()

# Set additional project information
set(COMPANY "Toyota")
set(COPYRIGHT "Copyright (c) 2017 Toyota Liu. All rights reserved.")
set(IDENTIFIER "com.toyota.Example")

include_directories(${Qt5Widgets_INCLUDE_DIRS})

add_library(mainwindow mainwindow.cpp)
target_link_libraries(mainwindow Qt5::Widgets)

add_project_meta(META_FILES_TO_INCLUDE)

add_executable(testM ${OS_BUNDLE} main.cpp ${META_FILES_TO_INCLUDE})
target_link_libraries(testM mainwindow)

# qt5_use_modules(helloworld Widgets)

