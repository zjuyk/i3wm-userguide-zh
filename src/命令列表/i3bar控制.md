# i3bar 控制

每个 i3bar 实例的配置中有两个选项可以在运行时通过 i3 调用命令来更改。
命令 `bar hidden_​​state` 和 `bar mode` 允许分别设置每个 bar 的当前 hidden_​​state 模式选项。
还可以在隐藏状态和显示状态以及停靠模式和隐藏模式之间切换。
每个 i3bar 实例都可以通过指定 bar_id 来单独控制，如果没有给出，则对所有 bar 实例执行该命令。

**语法：**

```
bar hidden_state hide|show|toggle [<bar_id>]

bar mode dock|hide|invisible|toggle [<bar_id>]
```

**例子：**

```
# 在隐藏状态和显示状态之间切换
bindsym $mod+m bar hidden_state toggle

# 在停靠模式和隐藏模式之间切换
bindsym $mod+n bar mode toggle

# 设置id为'bar-1'的bar实例切换到隐藏模式
bindsym $mod+b bar mode hide bar-1

# 将 id 为 'bar-1' 的 bar 实例设置为始终隐藏
bindsym $mod+Shift+b bar mode invisible bar-1
```