## Rust安装



```shell
（1）安装rustup
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
# 直接回车默认安装就行

(2)选择相应nightly版本进行下载
rustup toolchain install nightly-YYYY-MM-DD
# 请将YYYY-MM-DD替换为你找到的实际版本号。

（3）设置默认使用的rust版本
rustup default set nightly-YYYY-MM-DD

（4）安装工具包
cargo install cargo-binutils

（5）Rust中安装bare-metal目标
rustup target add riscv64gc-unknown-none-elf
# 根据目的进行替换
```

