# 路由管理器

<PluginInfo name="client"></PluginInfo>

## 介绍

路由管理器是一个用于管理系统主页面路由的工具，支持`桌面端`和`移动端`。使用路由管理器创建的路由，会同步显示在菜单中（可配置为不显示在菜单中）。反之，在页面菜单处添加的菜单，也会同步显示在路由管理器列表中。

![20250107115449](https://nocobase-docs.oss-cn-beijing.aliyuncs.com/20250107115449.png)

## 使用手册

### 路由类型

系统支持四种类型的路由：

- 分组（group）：用于对路由进行分组管理，可以包含子路由
- 页面（page）：系统内部页面
- 标签（tab）：用于在页面内部进行标签页切换的路由类型
- 链接（link）：内部或者外部链接，可直接跳转到其配置的链接地址

### 添加路由

点击右上角的“Add new”按钮可以创建新的路由：

1. 选择路由类型（Type）
2. 填写路由标题（Title）
3. 选择路由图标（Icon）
4. 设置是否在菜单中显示（Show in menu）
5. 设置是否开启 Tab 页（Enable page tabs）
6. 对于页面类型，系统会自动生成唯一的路由路径（Path）

![20250124131803](https://nocobase-docs.oss-cn-beijing.aliyuncs.com/20250124131803.png)

### 路由操作

每个路由条目支持以下操作：

- Add child：添加子路由
- Edit：编辑路由配置
- View：查看路由页面
- Delete：删除路由

### 批量操作

顶部工具栏提供以下批量操作功能：

- Refresh：刷新路由列表
- Delete：删除选中的路由
- Hide in menu：在菜单中隐藏选中的路由
- Show in menu：在菜单中显示选中的路由

### 路由筛选

使用顶部的“Filter”功能可以根据需要筛选路由列表。

:::info{title=提示}
路由配置的修改将直接影响系统的导航菜单结构。请谨慎操作，确保路由配置的正确性。
:::