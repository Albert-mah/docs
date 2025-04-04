# 弹窗

## 介绍

弹窗是页面上的一个小窗口，用于在当前页面中显示一些扩展的内容，可以以抽屉或对话框的形态呈现，例如某个订单详情或商品详情，也可以用于编辑数据。弹窗操作在 NocoBase 界面配置中扮演着非常重要的角色。很多区块都会提供各种弹窗操作，可以用于添加、查看、编辑数据等。同时也可以自定义各种弹窗操作来适应各种场景和需求。

## 类型和尺寸

> 在 v1.3.0-alpha 及以上的版本，支持以[页面](/handbook/ui/pop-up#页面)的方式打开。

弹窗有抽屉和对话框两种类型，在打开弹窗的操作上配置弹窗的类型和尺寸。

<video width="100%" height="440" controls>

 <source src="https://static-docs.nocobase.com/z-2024-06-13-09.43.42-2024-06-13-09-44-18.mp4">

</video>

### 抽屉

![2024-06-13_09-45-33-2024-06-13-09-46-11](https://static-docs.nocobase.com/2024-06-13_09-45-33-2024-06-13-09-46-11.png)

### 对话框

![2024-06-13_09-45-56-2024-06-13-09-46-20](https://static-docs.nocobase.com/2024-06-13_09-45-56-2024-06-13-09-46-20.png)

### 页面

:::info{title=提示}
需要 NocoBase 的版本是 v1.3.0-alpha 及以上。
:::

![20240809170648](https://static-docs.nocobase.com/20240809170648.png)

## 使用场景

弹窗目前的主要场景有：

- 区块的弹窗操作，可以用于添加、查看、编辑区块的数据；
- 关系数据的弹窗操作，可以用于查看和编辑关系数据的扩展信息。

### 区块的弹窗操作

![20240511141127](https://static-docs.nocobase.com/20240511141127.png)

### 关系数据的弹窗操作

![20240511141247](https://static-docs.nocobase.com/20240511141247.png)

### 对外分享单条记录的数据

:::info{title=提示}
需要 NocoBase 的版本是 v1.3.0-alpha 及以上。
:::

如果想跟其他人分享单条记录的数据，可以在打开弹窗之后，直接复制浏览器地址栏的 URL，然后分享给其他人。当其他人打开这个 URL 后，会在页面中自动弹出对应的弹窗。

![20240809173339_rec_](https://static-docs.nocobase.com/20240809173339_rec_.gif)

## 添加区块

弹窗中的添加区块，目前可以用于添加以下类型区块。

![20240511141349](https://static-docs.nocobase.com/20240511141349.png)

弹窗中的数据分为了三个维度：

- 当前记录：用于展示当前记录；
- 关系记录：用于展示与当前记录有关的关系数据；
- 其他记录：用于展示其他表的数据；

![20240511141442](https://static-docs.nocobase.com/20240511141442.png)

### 当前记录

示例：展示当前订单数据。

![20240511141809](https://static-docs.nocobase.com/20240511141809.gif)

### 关系记录

示例：展示当前订单关联的商品数据。

![20240511143040](https://static-docs.nocobase.com/20240511143040.gif)


### 其他记录

示例：订单表格区块的弹窗操作中配置仓库详情区块。

![20240511143415](https://static-docs.nocobase.com/20240511143415.gif)

## 使用变量

- 行操作的弹窗：每个弹窗都会有个「当前弹窗记录」变量，表示当前行记录。
- 关系字段的弹窗：每个弹窗都会有个「当前弹窗记录」变量，表示当前点击的关系记录。

弹窗里的区块都可以使用「当前弹窗记录」这个变量，相关使用场景有：

- 配置区块的数据范围
- 配置关系字段的数据范围
- 配置字段的默认值（新增数据的表单）
- 配置操作的联动规则
- 表单提交操作的字段赋值配置


更多内容参考 [变量](/handbook/ui/variables)
