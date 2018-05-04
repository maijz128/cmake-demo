# 指定运行此配置文件所需的 CMake 的最低版本号
cmake_minimum_required (VERSION 2.8)

# 项目信息：名称
project (Demo01)

# 指定生成目标：将名为 main.cc 的源文件编译成一个名称为 Demo01 的可执行文件。
add_executable(Demo01 main.cc)