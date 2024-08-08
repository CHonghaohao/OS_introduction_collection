# 介绍

​        本资料集用于李栋老师课题组入门培训使用，希望大家能够踊跃提交pr，以丰富我们的资料集。



# 使用

​        本资料集的使用需要安装mdbook环境，可以先安装Rust环境，可参考该教程[Rust安装](./setup/Rust安装.md)。安装完Rust环境后可以使用`cargo install mdbook`命令安装mdbook环境。

​        mdbook 的命令行使用方式很简单，简单几个参数就能完成 book 的初始化以及构建。

- mdbook init 仓库名：初始化当前仓库。会创建 book 目录，生成的文件默认都放在该目录中。而源 markdown 文件都放在 src 目录中，SUMMARY.md 就是一个目录文件，管理所有的章节，SUMMARY.md 中尽量都使用相对路径。book.toml 就是配置文件。配置参数后面会详细解释一下。
- mdbook build：构建书籍，会在 book 目录中生成 html 的文件
- mdbook serve --open：打开默认浏览器，通过一个 http server，在浏览器上预览该书籍。



------



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
