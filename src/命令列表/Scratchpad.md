# Scratchpad

有两个命令可以将任何现有窗口用作便笺窗口。`move scratchpad` 将一个窗口移动到暂存器工作区。
这将使它不可见，直到你再次显示它。你将无法打开该工作区。
相反，当使用 `scratchpad show` 时，窗口将再次显示为浮动窗口，以你当前的工作区为中心（在可见的便签簿窗口上使用 `scratchpad show` 将使其再次隐藏，因此你可以使用键绑定来切换）。
请注意，这只是一个普通的浮动窗口，因此如果你想“将其从便笺窗口中删除”，你可以简单地使其再次平铺（`floating toggle`）。

顾名思义，这对于拥有一个随时可用的带有你最喜欢的编辑器的窗口很有用。
但是，你也可以将它用于你不想一直看到的其他永久运行的应用程序：你的音乐播放器、alsamixer，甚至是邮件客户端……？

语法：

```
move scratchpad

scratchpad show
```

例子：

```
# 使当前聚焦的窗口成为便笺簿
bindsym $mod+Shift+minus move scratchpad

# 显示第一个便笺簿窗口
bindsym $mod+minus scratchpad show

# 显示 sup-mail 暂存窗口，如果有的话。
bindsym mod4+s [title="^Sup ::"] scratchpad show
```