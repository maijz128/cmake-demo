
# 查找当前目录下的所有源文件
# 并将名称保存到 DIR_SRCS_MATH 变量
aux_source_directory (. DIR_SRCS_MATH)

# 生成静态链接库
add_library (MathFunctions ${DIR_SRCS_MATH})
