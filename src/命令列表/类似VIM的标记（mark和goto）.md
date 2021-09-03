# 类似 VIM 的标记（mark 和 goto）

此功能类似于跳转功能：它允许你直接跳转到特定窗口（这意味着切换到适当的工作区并将焦点设置到窗口）。
但是，你可以使用任意标签直接标记特定窗口，然后再使用它。
你可以使用 unmark 命令以相同的方式取消标记标签。
如果你不指定标签，取消标记将删除所有标记。
你不需要确保你的窗口具有唯一的类或标题，也不需要更改你的配置文件。

由于该命令需要包含要用于标记窗口的标签，因此不能简单地将其绑定到一个键。
`i3-input` 是为此目的创建的工具：它允许你输入命令并将命令发送到 i3。
它还可以为该命令添加前缀并为输入对话框显示自定义提示。

如果窗口已经有这个标记，附加的 `--toggle` 选项将删除该标记，否则将添加它。
请注意，你可能需要将此与 `--add`（见下文）结合使用，否则任何其他标记都将被删除。

`--replace` 参数使 i3 删除任何现有标记，这也是默认行为。
你可以使用 `--add` 标志在窗口上放置多个标记。

如果你不想在窗口装饰中显示标记，请参阅 [显示标记](https://zjuyk.site/i3wm-userguide-zh/%E9%85%8D%E7%BD%AEi3/%E5%9C%A8%E7%AA%97%E5%8F%A3%E8%A3%85%E9%A5%B0%E7%BB%98%E5%88%B6%E6%A0%87%E8%AE%B0.html)。

**语法：**

```
mark [--add|--replace] [--toggle] <identifier>
[con_mark="identifier"] focus
unmark <identifier>
```

你可以使用 `i3-input` 提示输入标记名称，然后使用 `mark` 和 `focus` 命令创建并跳转到自定义标记：

**例子：**

```
# 读取 1 个字符并用该字符标记当前窗口
bindsym $mod+m exec i3-input -F 'mark %s' -l 1 -P 'Mark: '

# 读取 1 个字符并转到带有该字符的窗口
bindsym $mod+g exec i3-input -F '[con_mark="%s"] focus' -l 1 -P 'Goto: '
```

或者，如果你不想弄乱 `i3-input`，你可以为一组特定的标签创建单独的绑定，然后只使用这些标签：

**例子（在终端）：**

```
# 标记焦点容器
mark irssi

# 从任何有它的容器中删除标记“irssi”
'[con_mark="irssi"] focus'

# remove the mark "irssi" from whichever container has it
unmark irssi

# 删除所有 firefox 窗口上的所有标记
[class="(?i)firefox"] unmark
```