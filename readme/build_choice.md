选用任意一个裸机目标来编译。比如对 thumbv7em-none-eabihf，我们使用以下命令：

cargo build --target thumbv7em-none-eabihf
另外，我们也可以选择以本地操作系统为目标进行编译：

# Linux
cargo rustc -- -C link-arg=-nostartfiles
# Windows
cargo rustc -- -C link-args="/ENTRY:_start /SUBSYSTEM:console"
# macOS
cargo rustc -- -C link-args="-e __start -static -nostartfiles"