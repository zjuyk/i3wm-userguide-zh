# 移动容器或工作区到 RandR 输出

要移动一个容器到另一个 RandR 输出（用类似 `LVDS1` 和 `VGA1` 的名字标识），或者用方向标识的 RandR 输出，有两个命令可用：

```
move container to output left|right|down|up|current|primary|<显示输出>
move workspace to output left|right|down|up|current|primary|<显示输出>
```

例如：
```
# 移动目前工作区到下一个输出（如果你只有两个输出，相当于在两个输出之间切换）
bindsym $mod+x move workspace to output right

# 将此窗口移动到投影仪输出
bindsym $mod+x move container to output VGA1

# 将此窗口移到主输出
bindsym $mod+x move container to output primary
```

注意，你可能还没有一个主显示输出。运行以下命令以指定一个：
```
xrandr --output <显示输出> --primary
```
