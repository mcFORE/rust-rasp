# [如何在Raspberry Pi上安装Rust](https://www.makeuseof.com/tag/getting-started-rust-raspberry-pi/)

如果您对编程感兴趣，那么您可能已经听说过Rust。该语言由Mozilla设计，并受到开发人员的广泛喜爱。
Raspberry Pi是瑞士军刀般的小型计算机，非常适合学习代码。
让我们将两者结合起来，在Raspberry Pi上安装Rust。

## 安装Rust
- 安装
```
curl --proto '=https'  -sSf https://sh.rustup.rs | sh  # to install rustc and cargo (HOME dir)
source $HOME/.cargo/env                                              # to configure the current shell (PATH env)
```

- 检查
```
rustc --version
cargo --version
```

- 升级
```
rustup update
```

## 创建一个Rust项目
```
mkdir -p ~/rust # to creat the dir for rust projects
cd rust

cargo new po # to creat the first project
```

新生成的`po`文件夹:
```
├── Cargo.toml
└── src
    └── main.rs
```

其中, `Cargo.toml`文件为项目信息，构建说明和依赖项等:
```
[package]
name = "po"
version = "0.1.0"
authors = ["pi"]
edition = "2018"

[dependencies]
```

更多定义请参考: https://doc.rust-lang.org/cargo/reference/manifest.html

而`src/main.rs`为:
```
fn main() {
    println!("Hello, world!");
}
```

## 构建示例项目
```
cargo build --release
```

注意,
- 不加`release`的话, 默认发布为`debug`版本;
- 也可以`cargo run`直接运行;
- `build`之前, 可以先`cargo check`检查一下依赖是否完整和代码能否编译.

## TODO
这整个过程与在PC或服务器上使用rust没有任何不同?!
那么, 不同会在哪里, 相关的库??
