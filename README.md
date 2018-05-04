# CMake入门实战

> [《CMake入门实战》](http://www.hahack.com/codes/cmake/)
>
> [源代码](https://github.com/wzpan/cmake-demo)



**目录**

- Demo01：单个源文件

- Demo02：同一目录，多个源文件

- Demo03：多个目录，多个源文件

- Demo04：自定义编译选项

  ```shell
  cmake -USE_MYMATH=OFF .
  ```

- Demo05：安装和测试

- Demo06：添加环境检查

- Demo07：添加版本号

- Demo08：生成安装包



**生成项目**

```shell
cd Demo01
cmake .
```



**编译项目**

```shell
cmake --build .
```



**测试项目**

```shell
ctest
```

or

```shell
make test
```



**生成安装包**

生成二进制安装包：

```shell
cpack -C CPackConfig.cmake
```

生成源码安装包

```shell
cpack -C CPackSourceConfig.cmake
```

