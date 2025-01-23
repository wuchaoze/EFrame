cmake_minimum_required(VERSION 3.16)

#project(ENetWork VERSION 0.1 LANGUAGES CXX)
# 设置 C++ 标准
#set(CMAKE_CXX_STANDARD 17)
#set(CMAKE_CXX_STANDARD_REQUIRED ON)

# 自动处理 Qt 的元对象编译器（moc）、资源编译器（rcc）和用户界面编译器（uic）
#set(CMAKE_AUTOMOC ON)
#set(CMAKE_AUTORCC ON)
#set(CMAKE_AUTOUIC ON)

# 子工程的源文件
set(ENetWork_SOURCES
    udpsocketbase.cpp
    udpsocketbase.h

)
# 添加子工程的目标（假设子工程是一个库）
#add_library(ENetWork ${ENetWork_SOURCES})
set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_PREFIX_PATH "F:/Qt/Qt6.7/6.8.0/msvc2022_64")          #视Qt的具体情况改变
set(ENetWork_SOURCES ${ENetWork_SOURCES} PARENT_SCOPE)


# 查找 Qt 模块
find_package(Qt${QT_VERSION_MAJOR} REQUIRED COMPONENTS Network)
# 链接 Qt 网络模块
target_link_libraries(NetworkModule PRIVATE Qt${QT_VERSION_MAJOR}::Network)