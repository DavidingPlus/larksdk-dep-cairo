# larksdk-dep-cairo

编译 [LarkSDK](https://gitee.com/cytech_05/larksdk) 需要的 Cairo 依赖库。

目前只有 Linux 下会出现问题，Windows 运行正常。

目前仅支持 Cairo 1.18.0，不支持多版本。后续根据 LarkSDK 需求扩展。

项目中的 conandata.yml 和 conanfile.py 均由 Conan 官方 [Recipe](https://github.com/conan-io/conan-center-index/tree/master/recipes/cairo/all) 修改而来。

