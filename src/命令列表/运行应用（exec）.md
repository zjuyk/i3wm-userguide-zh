# 运行应用（exec）

如果你不能实际启动任何应用程序，那么窗口管理器有什么用呢？exec 命令通过将你指定的命令传递给 shell 来启动一个应用程序。这意味着你可以使用通配符，并将会在 `$PATH` 中搜索程序。

格式：
```
exec [--no-startup-id] <命令>
```

举例：
```
# 打开 GIMP
bindsym $mod+g exec gimp

# 打开还不支持启动通知的终端模拟器 urxvt
bindsym $mod+Return exec --no-startup-id urxvt
```

`--no-startup-id` 参数禁用了对这个 exec 命令的启动通知支持。通过使用启动通知，i3 可以确保程序的窗口在你使用 exec 命令时所在的工作区中出现。同时，它还会在应用程序启动时将 X11 光标改为 watch（一个时钟）。所以，如果一个应用程序没有支持启动通知（不过大多数使用 GTK 和 Qt 的应用程序似乎都支持），将会出现 60 秒的时钟光标。

如果要执行的命令包含 `;`（分号）或 `,`（逗号），那么整个命令必须被引号包裹。例如，要为 shell 命令 `notify-send Hello, i3` 设置一个绑定，你可以在你的配置文件中添加这样一个条目：

```
# 运行一个包含逗号的命令
bindsym $mod+p exec "notify-send Hello, i3"
```

如果一个带有逗号和/或分号的命令本身需要引号，你必须用双反斜线转义内部引号，像这样：

```
# 运行一个包含逗号、分号和引号的命令
bindsym $mod+p exec "notify-send \\"Hello, i3; from $USER\\""
```
