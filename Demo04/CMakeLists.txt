# CMake 最低版本号要求
cmake_minimum_required (VERSION 2.8)

# 项目信息
project (Demo4)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

# 加入一个配置头文件，用于处理 CMake 对源码的设置
configure_file(
	"${PROJECT_SOURCE_DIR}/config.h.in"
	"${PROJECT_BINARY_DIR}/config.h"
)

# 是否使用自己的 MathFunctions 库
option (USE_MYMATH
		"Use provided math implementation" ON)
		
# 是否加入 MathFunctions 库
if (USE_MYMATH)
	include_directories ("${PROJECT_SOURCE_DIR}/math")
	add_subdirectory (math)
	set (EXTRA_LIBS ${EXTRA_LIBS} MathFunctions)
endif (USE_MYMATH)

# 查找当前目录下的所有源文件
# 并将名称保存到变量
aux_source_directory (. DIR_SRCS)

# 指定生成目标
add_executable (Demo ${DIR_SRCS})
target_link_libraries (Demo ${EXTRA_LIBS})


# 解释
# 第7行的 configure_file 命令用于加入一个配置头文件 config.h ，这个文件由 CMake 从 config.h.in 生成，通过这样的机制，将可以通过预定义一些参数和变量来控制代码的生成。
# 第13行的 option 命令添加了一个 USE_MYMATH 选项，并且默认值为 ON 。
# 第17行根据 USE_MYMATH 变量的值来决定是否使用我们自己编写的 MathFunctions 库。
# 开关：cmake -USE_MYMATH=OFF .
