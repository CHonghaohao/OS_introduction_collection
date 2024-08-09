# OS内核教程
## 实验环境

![image-20240304195931843](https://s2.loli.net/2024/03/04/q6kGXaDIiWpCAnJ.png)

64位RISCV



## 教材

其实大部分教材都是参考作用，平台和我们不一样。

教材链接：https://wwi.lanzoup.com/b00sdj5qh（密码：7dr3）



## 操作系统真象还原

bochs平台，32位x86处理器。但讲得比较详细，可以参考下实现思路。



## 语言基础

[Rust学习与使用](./Rust学习与使用.md)



## 基础环境的安装

- [Rust安装](./setup/Rust安装.md)
- [Qemu安装](./setup/Qemu编译安装.md)
- [交叉编译工具链安装](./setup/交叉编译工具链安装.md)
- [Linux内核编译](./setup/Linux内核编译.md)
- [OpenSBI编译](./setup/OpenSBI编译.md)
- [制作rootfs](setup/制作rootfs.md)：该教程比较简单，若希望制作复杂的rootfs可参考该资料：[rootfs制作](https://www.cnblogs.com/wsg1100/p/13127636.html)

最终目标：可以使用上述环境使用qemu 运行一个riscv或arm架构的linux。

运行命令：

```shell
qemu-system-riscv64 \
    -M virt \
    -nographic \
    -smp 8 \
    -m 8G \
    -bios path/to/fw_jump.elf \
    -kernel path/to/Image \
    -append "root=/dev/vda rw console=ttyS0" \
    -drive file= path/to/ubuntu_riscv64.img,if=none,format=raw,id=hd0 \
    -device virtio-blk-device,drive=hd0
```

其中fw_jump.elf、Image、ubuntu_riscv64.img需要根据自己实际编译出的文件进行替换。

## Linux内核设计与实现

[Linux内核设计与实现](./linux_kernel/Linux内核设计与实现.md)



## Hypervisor

[Hypervisor入门](./hypervisor/Hypervisor入门.md)



------



# Contributors

[Contributors](misc/contributors.md)
