# i3bar 命令

默认情况下，i3 会直接将 `i3bar` 传到你的 shell 来处理、搜索 `$PATH` 以找到正确的版本。如果你在某个地方有一个不同的 `i3bar` 或者二进制文件不在 `$PATH` 里，你可以告诉 i3 执行哪个文件。

这个特定的命令会被传到 `sh -c` 执行，因此你可以使用通配符，且必须使用正确的引号等。

**语法：**

```
i3bar_comand <command>
```

**例子：**

```
bar {
    i3bar_command /home/user/bin/i3bar
}
```
