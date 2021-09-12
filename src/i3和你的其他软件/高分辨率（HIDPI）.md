# 高分辨率（HIDPI）

有关如何在 Linux 桌面的各个部分启用缩放的详细信息，请参阅 [https://wiki.archlinux.org/index.php/HiDPI](https://wiki.archlinux.org/index.php/HiDPI)。i3 会从 Xft.dpi 属性读取所需的 DPI 值。该属性默认为 96 DPI，因此要实现 200% 缩放，你需要在 `~/.Xresources` 中设置 Xft.dpi: 192。

如果你是刚得到新显示器的 i3 用户，请仔细确认：

- 你在 i3 配置中使用了可缩放字体（以 "pango:" 开头）。
- 你正在使用支持缩放的终端模拟器。你可以暂时切换到 gnome-terminal，它以支持开箱即用的扩展而闻名，直到你弄清楚如何在你最喜欢的终端模拟器中调整字体大小。
