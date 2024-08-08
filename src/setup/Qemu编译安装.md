## Qemu源码安装

```shell
prepare:
sudo apt install python3-venv ninja-build pkg-config python3-pip libglib2.0-dev nettle-dev

pip install sphinx-rtd-theme


（1）下载源码
wget https://download.qemu.org/qemu-8.2.0.tar.xz

（2）解压
tar xvJf qemu-7.2.12.tar.xz

（3）配置
./configure --target-list=riscv64-softmmu,riscv64-linux-user --enable-kvm --enable-nettle --enable-user --enable-linux-user --enable-slirp

（4）编译
make -j$(nproc)

（5）安装
make install

```

