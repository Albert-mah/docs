# 多关键词筛选<Badge>v1.7.0+</Badge>

<PluginInfo commercial="true" name="multi-keyword-filter"></PluginInfo>

## 介绍

**多关键词筛选**插件为 NocoBase 平台增加了强大的文本筛选功能，让您能够使用多个关键词进行筛选，大大提高了数据查询的灵活性和效率。

该插件主要提供两个筛选操作符：
- **等于任意一个**：筛选包含指定关键词列表中任意一个的记录
- **不等于任意一个**：筛选不包含指定关键词列表中任意一个的记录

这两个操作符可用于以下字段：
- 单行文本
- 手机号
- 邮箱
- 整数
- 数字
- 百分比
- UUID
- Nano ID
- 自动编码

## 应用场景

- 需要根据多个产品编码、标签或分类进行筛选
- 从 Excel 文件导入大量关键词进行批量筛选
- 需要快速查找符合多个条件的数据记录

## 使用范围

- 筛选表单区块的字段
![20250417170714](https://static-docs.nocobase.com/20250417170714.png)
- 筛选按钮的字段
![20250417170923](https://static-docs.nocobase.com/20250417170923.png)
- 数据范围筛选的字段
![20250417171011](https://static-docs.nocobase.com/20250417171011.png)
- 联动规则的字段
![20250417171124](https://static-docs.nocobase.com/20250417171124.png)

## 如何使用

### 1. 添加单行文本字段

以筛选表单和单行文本为例，将单行文本字段的操作符设置为"等于任意一个"或"不等于任意一个"

![20250417165918_rec_](https://static-docs.nocobase.com/20250417165918_rec_.gif)

### 2. 输入关键词

有两种方式可以输入关键词：

#### 2.1 手动输入

1. 在输入框中直接输入关键词
2. 多个关键词可以用换行符分隔
3. 输入完成后，点击筛选按钮对数据进行筛选

#### 2.2 从 Excel 导入关键词

1. 准备一个 Excel 文件(支持 .xlsx 或 .xls 格式)，包含需要导入的关键词
2. 点击输入框右侧的"导入 Excel"按钮
3. 选择并上传 Excel 文件

**如果 Excel 只有一列数据**：
- 系统将自动导入该列所有非空值作为关键词

**如果 Excel 包含多列数据**：
- 系统会弹出列选择对话框
- 可以选择一列或多列进行导入
- 选择单列：该列中所有非空值将被导入为关键词
- 选择多列：多列中的非空值将被合并为关键词，重复值会被自动去除
- 点击"确认"按钮完成导入

![20250417170324_rec_](https://static-docs.nocobase.com/20250417170324_rec_.gif)

### 3. 筛选效果

- **等于任意一个**：字段值与关键词列表中任一值匹配的记录都会被显示
- **不等于任意一个**：字段值与关键词列表中所有值都不匹配的记录会被显示

## 常见问题解答

### 如何清除已添加的关键词？

点击关键词标签上的"×"按钮可删除单个关键词，或者点击输入框右侧的"×"删除所有关键词。

![20250417165604](https://static-docs.nocobase.com/20250417165604.png)

### 可以导入多少个关键词？

插件支持大量关键词的导入，但建议控制在合理范围内（如数百个），以免影响查询性能。

### 导入的关键词格式有什么要求？

- Excel 文件应包含至少一列数据
- 空值会被自动过滤
- 重复值会被自动去除

### 是否支持模糊匹配？

该插件提供的是精确匹配功能。

### 哪些字段支持这个功能？

- 单行文本
- 手机号
- 邮箱
- 整数
- 数字
- 百分比
- UUID
- Nano ID
- 公式
- 自动编码

## 提示和技巧

- 将常用的关键词列表保存在 Excel 文件中，需要时快速导入
- 选择多列导入时，可以合并来自不同列的关键词
- 使用"不等于任意一个"操作符可以快速排除不需要的数据

## 系统要求

- NocoBase 版本：1.7.0 或更高版本

---

通过使用多关键词筛选插件，您可以更高效地管理和查询数据，特别是在处理大量数据和需要频繁进行多条件筛选的场景下，该插件将显著提升您的工作效率。
