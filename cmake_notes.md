### introduction for CMAKE
---
构建环境太恶心，CMAKE可以进行环境的整理和汇总，在使用不同库时都可以有很好的效果，同时QT和VScode也支持CMAKE的环境构建，所以学习这个是很有必要的
---
### CMake Tutorial
1. 一般来说C++ Project包括include头文件;lib库文件;build构建项目目录;src源代码文件夹;bine二进制程序文件夹;CMakeLists.txt编译环境设置，首先需要编写CMakeLists.txt来进行环境的基本构建
2. 常用CMAKE代码：
   1. `cmake .. && make #在build目录下使用，用于生成可执行二进制文件`
   2. `cmake_minimum_required(VERSION 3.16) #cmake版本设置`
   3. `PROJECT(project) #工程名设置`
   4. `INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/include) #设定头文件目录`
   5. `SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin) #设定可执行文件放置的目录`
   6. `LINK_DIRECTORIES(${PROJECT_SOURCE_DIR}/lib) #设定第三方库目录`
   7. `ADD_SUBDIRECTORY(${PROJECT_SOURCE_DIR}/src) #添加源代码文件夹进行继续构建`
   8. `add_executable(test main.cpp) #添加可执行文件`
3. 因为file()函数是CMake中常用的一个函数，包括创建、删除、复制、移动、比较等操作，所以单独列一条：
   1. `file(GLOB SOURCES src/*.cpp) #`
4. 内部编译和外部编译：可以在根目录直接cmake .也可以在build文件夹cmake ..，但外部编译对于每次的调试以及编译内容和源代码隔离有很大的好处,推荐外部编译
5. 