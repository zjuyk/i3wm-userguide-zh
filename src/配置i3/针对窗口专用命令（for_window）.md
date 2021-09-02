# 针对窗口专用命令（for_window）

使用 `for_window` 指令，你可以让 i3 在遇到特定窗口时执行任何命令。例如，将窗口设置为浮动或更改其边框样式。

**语法**：

```
for_window <criteria> <command>
```

**例子**：

```
# 对所有的 XTerm 窗口开启浮动模式
for_window [class="XTerm"] floating enable

# 使所有的 urxvt 窗口的边框为 1 像素：
for_window [class="urxvt"] border pixel 1

# 一个很少用到但是很有趣的例子：
# 当我切换到 `~/work` 目录时使所有的窗口浮动
for_window [title="x200: ~/work"] floating enable
```

有效标准与命令的标准相同，请参阅 [command_criteria](../命令列表/命令列表.md)。在运行时只能执行命令，不能执行配置指令，请参阅 [list_of_commands](../命令列表/命令列表.md)。