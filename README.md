# larksdk-dep-cairo

编译 [LarkSDK](https://gitee.com/cytech_05/larksdk) 需要的 Cairo 依赖库。

目前 Linux 下会出现问题，无法直接拉打好的 Conan 包，可能是 Xorg/System 的问题。因此只能选择从源码编译，而国内下载远端的源码包太慢了。这里就是通过修改相关配置，能直接使用提前下载好的包进行编译。

Windows 下通过正常 Conan 流程能直接安装打好的包而不需要从源码编译。

目前仅支持 Cairo 1.18.0，不支持多版本。后续根据 LarkSDK 需求扩展。

项目中的 conanfile.py 和 conandata.yml 均由 Conan 官方 [Recipe](https://github.com/conan-io/conan-center-index/tree/master/recipes/cairo/all) 修改而来。

# 使用方法

下载 Release 到本地，下载 Source Code 即可。

在下载好的根目录中执行，建议使用 Conan 2：

```bash
conan export .
```

即可成功将 conanfile.py、conandata.yml 和 源码压缩包等编译所需的源文件打包到 ~/.conan2/p 目录中。后续在 LarkSDK 项目中 `conan install . --build=missing` 即可成功从本地编译，解决从远端下载包速度慢的问题。

> 这里不推荐使用 `conan export-pkg .` 命令，会安装 Cairo 所需的依赖。并且目前测试发现有问题，我也不知道为什么。后续有空再调研。

![conan-export-pkg](https://i-blog.csdnimg.cn/direct/8bd90cee73b94ab6be1153d1b054af90.png)

