# <div align="center">cpp-template</div>

<div align="center">

一个开箱即用、结构干净、适合在 VS Code 中直接生成与运行的 C++ 最小模板。

</div>

<div align="center">

![C++](https://img.shields.io/badge/C%2B%2B-17-0f172a?style=flat-square)
![CMake](https://img.shields.io/badge/CMake-3.16%2B-334155?style=flat-square)
![VS%20Code](https://img.shields.io/badge/VS%20Code-CMake%20Tools-2563eb?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-475569?style=flat-square)

</div>

## 介绍

`cpp-template` 是一个面向个人练习、小型项目和快速起步场景的 C++ 工程模板。

它保留了最常用、最稳定的部分：

- 用 `src/` 和 `include/` 分离源码与头文件
- 用 `CMake` 管理构建
- 用 `VS Code + CMake Tools` 完成配置、生成、运行
- 不写死本机编译器路径，方便复制后直接复用

如果你想要的是一个“不臃肿，但也不寒酸”的 C++ 起步仓库，这个模板就是为这个目的准备的。

## 特性

- 最小结构：没有多余目录，打开就能看懂
- 通用配置：不绑定某一台机器的编译器路径
- VS Code 友好：支持直接选择编译器并点击生成、运行
- 易于扩展：后续加 `tests/`、`cmake/`、库目标都很自然

## 目录结构

```text
cpp-template/
├── .vscode/
│   └── settings.json
├── include/
│   └── hello.h
├── src/
│   ├── hello.cpp
│   └── main.cpp
├── docs/
│   └── plans/
├── CMakeLists.txt
├── CMakePresets.json
├── .gitignore
└── README.md
```

## 快速开始

### 1. 准备环境

你至少需要：

- 一个可用的 C++ 编译器：`GCC`、`Clang` 或 `MSVC`
- `CMake`
- `VS Code`
- VS Code 扩展：
  - `CMake Tools`
  - `C/C++`

## 在 VS Code 中使用

### 1. 打开项目

直接用 VS Code 打开这个目录。

### 2. 选择编译器

按 `Ctrl+Shift+P`，执行：

```text
CMake: Select a Kit
```

然后选择你机器上可用的编译器，例如：

- `GCC`
- `Clang`
- `Visual Studio Build Tools`

如果这里没有看到任何编译器，通常是下面两个原因：

1. 编译器还没有安装
2. 编译器没有加入系统 `PATH`

处理完以后，重新打开 VS Code 再选一次即可。

### 3. 生成项目

选择完编译器后，可以直接点击 VS Code 底部状态栏中的 CMake 按钮完成：

- Configure
- Build

### 4. 运行程序

继续点击状态栏中的 Run 按钮即可运行当前可执行目标。

这个模板只保留了一个目标 `cpp-template`，所以不会出现运行目标混乱的问题。

### 5. 如果你是从旧工程改过来的

如果这个目录之前已经被 VS Code 的 CMake Tools 配置过一次，建议执行：

```text
CMake: Delete Cache and Reconfigure
```

这样可以清掉旧缓存，避免继续沿用之前的构建状态。

## 命令行构建

如果你不想依赖 VS Code，也可以直接在命令行里构建：

```bash
cmake -S . -B out/build/debug
cmake --build out/build/debug
```

运行程序：

```bash
./out/build/debug/cpp-template
```

在 Windows + MinGW 环境下，通常会生成：

```bash
./out/build/debug/cpp-template.exe
```

## 如何更换项目名

复制这个模板后，如果你想把它改成自己的项目名，通常只需要改两处：

1. [`CMakeLists.txt`](./CMakeLists.txt) 中的

```cmake
project(cpp-template VERSION 0.1.0 LANGUAGES CXX)
```

2. [`CMakeLists.txt`](./CMakeLists.txt) 中的

```cmake
add_executable(cpp-template
    src/main.cpp
    src/hello.cpp
)
```

然后把示例代码替换成你自己的逻辑即可。

## 适合什么场景

- C++ 练习项目
- 算法与数据结构练手
- 小工具开发
- 课程作业起步工程
- 想快速搭一个干净 CMake 工程的人

