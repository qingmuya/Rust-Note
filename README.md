# Rust-Note

 

## 编译

使用`rustc 文件名`即可编译代码，编译成功后会生成一个二进制文件：在windows上为exe，同时还会在Windows上生成一个.pdb文件，里面包含调试信息。



## Cargo

Cargo是rust的构建系统和包管理工具，用于构建代码、下载依赖的库、构建这些库等等



### 使用Cargo创建项目

使用命令`cargo new 项目名称`即可创建按项目

此时会创建一个新的目录，内部包含Cargo.toml、src目录（内部包含main.js）、初始化的一个Git仓库、.gitignore。

其中Cargo.toml是Cargo的配置格式，Toml是一种新兴的配置文件格式，Cargo.toml的内部初始化如下

```toml
[package]
name = "hello_cargo"
version = "0.1.0"
edition = "2021"

[dependencies]
```

其中`[pacakge]`是一个区域标题，表示下方内容是用来配置包的：name(项目名)、version(项目版本)、authors(项目作者)、edition(使用的Rust版本)。

`[dependencies]`，另一个区域的开始，它会列出项目的依赖项。

在rust中，代码的包称作crate。



### cargo build

使用cargo build命令后会创建可执行文件：`/target/debug/文件名.exe`

第一次运行`cargo build`会在顶层目录生成cargo.lok文件：该文件负责追踪项目依赖的精确版本，不需要手动修改该文件。



### cargo run

编译代码+执行结果



### cargo check

检查代码，确保能通过编译，但是不产生任何可执行文件，速度比cargo build快很多。



### 为发布构建

`cargo build --release`：编译时会进行优化