# 在Windows上编译并安装aseprite

这个页面如标题所示，在Windows上编译aseprite并安装。

## 安装的先决条件

1. 是Windows系统
2. 系统是x64位
3. 硬盘剩下储存大于10GiB

## 安装

**安装Visual Studio的时间可能会很长，请做好准备。**

### 安装所需软件

- 下载aseprite源码。
  1. 访问[*aseprite*的*Release*页面](https://github.com/aseprite/aseprite/releases)，下载**Aseprite-vx.x.x-Source.zip**（x为数字，以`Aseprite-v1.2.25-Source.zip`
为例）。
  2. 解压zip文件至任意地方（以`E:\aseprite\`为例）。
- 下载并安装cmake。
  1. 访问[*cmake*网站](https://cmake.org/download)，找到**Binary distributions**一行，下载**cmake-x.x.x-win64-x64.msi**可执行文件（x为数字）。
  2. 安装*cmake*。安装时需要点击`Add CMake to the system PATH for all users`选项，其他直接*Next*（CMake安装目录以`C:\Program Files\CMake`为例）。
- 下载ninja。
  1. 访问[*ninja*的*Release*页面](https://github.com/ninja-build/ninja/releases)，下载**ninja-win.zip**（以`v1.10.2`为例）。
  2. 将zip文件解压至*cmake*的`bin`目录下（在我的电脑上，我需要解压到`C:\Program Files\CMake\bin\`里）。
- 下载Skia。
  1. 访问[*Skia*的*Release*页面](https://github.com/aseprite/skia/releases)，下载**Skia-Windows-Release-x64.zip**（以`skia-m81`为例）。
  2. 解压zip文件至任意地方（以`E:\skia\`为例）。
- 下载并安装Visual Studio。 **这一步需要等待，所以不妨先把这个安装好。**
  1. 访问[*Visual Studio*网站](https://visualstudio.microsoft.com/zh-hans/vs/)，点击`下载Visual Studio`，选择`community xxxx`，下载文件（xxxx为数字）。
  2. 启动*Visual*安装程序，并等待启动。
  3. 勾选`使用C++的桌面开发`，检查单个组件中是否存在WIN 10 SDK的18362版本。
  4. 安装，并等待安装完成。
  5. 重新启动电脑。

### 编译aseprite源码

1. 在开始菜单中打开`Visual Studio xxxx`文件夹，点击启动`Developer Command Prompt for VS xxxx`（xxxx为数字）。
2. 在弹出的窗口中输入`cd /d aseprite源码路径`（在我的电脑上，我需要运行`cd /d E:\aseprite\`）并回车。
3. 运行`mkdir build`。
4. 运行`cd build`。
5. 运行`cmake -DCMAKE_BUILD_TYPE=RelWithDebInfo -DLAF_BACKEND=skia -DSKIA_DIR=Skia解压路径 -DSKIA_LIBRARY_DIR=Sika解压路径\out\Release-x64 -G Ninja ..`开始编译*aseprite*（如果你的电脑上有MinGW，请运行`cmake -DCMAKE_IGNORE_PATH=C:\MinGW\bin -DCMAKE_BUILD_TYPE=RelWithDebInfo -DLAF_BACKEND=skia -DSKIA_DIR=Skia解压路径 -DSKIA_LIBRARY_DIR=Sika解压路径\out\Release-x64 -G Ninja ..`或者**临时**在环境变量中删除MinGW）。
6. 运行`ninja aseprite`。

## 查收结果
如果以上命令都没有报错，那么恭喜你，*aseprite*已经准备好了！请在`bin`文件夹内找到编译好的`aseprite.exe`并运行。

-END-

#### 参考文献
**感谢以下作者！**
- [知乎的嘉暮Guexter](https://zhuanlan.zhihu.com/p/156775243)，本文章多处参考了嘉暮Guexter的文章。
- [Github上的aseprite团队](https://github.com/aseprite/)，给我们带来这么好的软件。

##### 碎碎念
~~汉化自己百度一下罢（~~
