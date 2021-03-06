# X 资源

[变量](./变量.md) 也可以使用在 X 资源数据库中配置的值来创建。
例如，这有助于避免在 i3 配置中配置颜色值。
相反，这些值可以在 X 资源数据库中配置一次，以在许多 X 应用程序中实现易于维护、一致的颜色主题。

定义一个资源将从资源数据库中加载该资源并将其值赋给指定的变量。
这是逐字完成的，因此值必须采用 i3 使用的格式。
如果无法从数据库加载资源，则必须指定回退。

语法：

```
set_from_resource $<name> <resource_name> <fallback>
```

例子：

```
# `~/.Xresources` 应该包含类似下行
#     *color0: #121212
# 同时正确加载，例如，通过
#     xrdb ~/.Xresources
# 该值被其他应用程序获取（例如 URxvt）和在 i3 配置文件中这样使用:
set_from_resource $black i3wm.color0 #000000
```