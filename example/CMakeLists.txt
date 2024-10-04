cmake_minimum_required(VERSION 3.6)
project(QCodeEditorExample)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_AUTOMOC On)
set(CMAKE_AUTORCC ON)

#find_package(QCodeEditor REQUIRED)
find_package(Qt6 COMPONENTS
    Core
    Gui
    Widgets
    REQUIRED)

add_library(QCodeEditor ..)

add_executable(QCodeEditorExample
    resources/demo_resources.qrc
    src/main.cpp
    src/MainWindow.cpp
    include/MainWindow.hpp
)

target_include_directories(QCodeEditorExample PUBLIC
    include
    ../include
)

target_link_libraries(QCodeEditorExample
    Qt6::Core
    Qt6::Widgets
    Qt6::Gui
    C:/dev/PockEmul/QCodeEditor/build/Desktop_Qt_6_7_3_MSVC2019_64bit-Release/QCodeEditor.lib
)
