#最低版本号
cmake_minimum_required(VERSION 3.0)

#项目名称
project(learn_lib)

#整合源文件
aux_source_directory(${PROJECT_BINARY_DIR}/../src SRC_DIR)

#引入头文件
include_directories(${PROJECT_BINARY_DIR}/../inc)

#查找库文件，参数1:库文件变量；参数2：库文件名称；参数3：查找的目录
find_library(LIB_DIR myfunc ${PROJECT_BINARY_DIR}/../lib)

#设置可执行文件生成位置
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/../bin)

#生成可执行文件
add_executable(libmain_test ${SRC_DIR})

#把库链接到可执行文件中
target_link_libraries(libmain_test ${LIB_DIR})

#
