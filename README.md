# 介绍

​        本资料集用于李栋老师课题组入门培训使用，希望大家能够踊跃提交pr，以丰富我们的资料集。



# 使用

​        本资料集的使用需要安装mdbook环境，可以先安装Rust环境，可参考该教程[Rust安装](./setup/Rust安装.md)。安装完Rust环境后可以使用`cargo install mdbook`命令安装mdbook环境。

​        mdbook 的命令行使用方式很简单，简单几个参数就能完成 book 的初始化以及构建。

- mdbook init 仓库名：初始化当前仓库。会创建 book 目录，生成的文件默认都放在该目录中。而源 markdown 文件都放在 src 目录中，SUMMARY.md 就是一个目录文件，管理所有的章节，SUMMARY.md 中尽量都使用相对路径。book.toml 就是配置文件。配置参数后面会详细解释一下。
- mdbook build：构建书籍，会在 book 目录中生成 html 的文件
- mdbook serve --open：打开默认浏览器，通过一个 http server，在浏览器上预览该书籍。

------

具体教程查看[OS内核教程](./src/README.md)
