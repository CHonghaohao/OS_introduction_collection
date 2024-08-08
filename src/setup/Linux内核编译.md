## Linux内核编译步骤

```shell
# 下载源码，使用v6.8-rc5版本
git clone https://github.com/avpatel/linux.git
cd linux

# 切换到目标分支
git checkout v6.8-rc5
make ARCH=riscv CROSS_COMPILE=riscv64-unknown-linux-gnu- defconfig

# 编译内核模块，这些模块可以在系统运行时动态加载
make ARCH=riscv CROSS_COMPILE=riscv64-unknown-linux-gnu- modules -j$(nproc)

# 编译内核映像，它是系统启动时加载并运行的内核核心部分
make ARCH=riscv CROSS_COMPILE=riscv64-unknown-linux-gnu- Image -j$(nproc)

# 生成的镜像在./arch/riscv/boot目录下
```

