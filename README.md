# 链接到系统库

此示例演示如何链接系统库以及如何使用构建脚本来支持此用例。
Rust crate 经常希望链接到系统上提供的本机库以绑定其功能或仅将其用作实现细节的一部分。当以与平台无关的方式执行此操作时， 这是一个非常微妙的问题。
如果可能的话，最好尽可能多地分出这些内容，以使消费者尽可能容易地做到这一点。对于此示例，我们将创建与系统 zlib 库的绑定。
这是一个在大多数提供数据压缩的类 Unix 系统上常见的库。这已经包含在libz-sys crate 中，但对于这个例子，我们将做一个非常简化的版本。
查看完整示例的[源代码](https://github.com/rust-lang/libz-sys)。
为了便于查找库的位置，我们将使用 pkg-configcrate。这个 crate 使用系统的pkg-config实用程序来发现有关图书馆的信息。它会自动告诉 Cargo 需要什么来链接库。这可能只适用于pkg-config已安装的类 Unix 系统。

参考[教程](https://doc.rust-lang.org/cargo/reference/build-script-examples.html#linking-to-system-libraries)