# -
z170x-gaming5 i36100

下载下面的系统镜像
https://mirrors.dtops.cc/iso/MacOS/daliansky_macos/macOS%20Catalina%2010.15.7%2819H2%29%20Installer%20for%20Clover%205122%20and%20WEPE.dmg

安装好了要在Clover里面进行HD530的显卡，再重启，基本就可以用了

现在发现的问题是睡眠不完美，其他的没发现什么大问题

我用网线上网的，没问题。

关机之后会自动重启
这个问题的解决办法就是使用Clover Configurator打开config.plist文件并勾选Acpi部分的FixShutdown选项。

WiFi使用一段时间之后就会无法联网
这个问题同样跟BIOS的设置有关，设置 Wake on LAN 为 Disabled就可以解决。

睡眠之后无法唤醒屏幕
解决这个问题需要在config.plist中设置darkwake=0，意思就是禁用Mac的Power Nap功能。对于darkwake这个参数的其他值的意义可以查看这篇文章Power Nap功能与Darkwake参数。

睡眠之后又会立刻唤醒
这个问题其实跟USB有关，当我选择睡眠之后拔掉鼠标和键盘等USB设备之后就能正常的睡眠了。我之前 BIOS中设置Legacy USB Support 为 enabled，当我尝试把它改成Auto之后睡眠的问题就解决了。
