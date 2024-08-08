## OpenSBI编译步骤

```shell
# 源码下载
git clone https://github.com/riscv-software-src/opensbi.git
cd opensbi/

# 切换到目标版本
git checkout v1.2

make PLATFORM=generic CROSS_COMPILE=riscv64-unknown-linux-gnu-

# 编译完后，在opensbi/build/platform/generic/firmware/目录下
```

生成的固件有三种类型：dynamic、jump和payload

- dynamic：带有动态信息的固件
- jump：指定下一级的boot地址跳转
- payload：包含下一级boot的二进制内容，通常是uboot/linux
  这里我们使用jump类型固件（fw_jump.elf），OpenSBI运行后，可以直接跳转到kernel运行。

因为opensbi本身就是一个bootloader，因此可以不使用uboot引导kernel，通过opensbi的jump固件，可以直接跳转到kernel启动。

