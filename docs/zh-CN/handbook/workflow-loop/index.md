# 循环

<PluginInfo name="workflow-loop" link="/handbook/workflow-loop"></PluginInfo>

循环相当编程语言中的 `for`/`while`/`forEach` 等语法结构，当需要一定次数或针对某个数据集合（数组）重复执行一些操作时，可以使用循环节点。

## 安装

内置插件，无需安装。

## 使用手册

### 创建节点

在工作流配置界面中，点击流程中的加号（“+”）按钮，添加“循环”节点：

![创建循环节点](https://static-docs.nocobase.com/b3c8061a66bfff037f4b9509ab0aad75.png)

创建循环节点后，会生成一个循环内部的分支，可以在分支中增加任意多个节点，这些节点除了可以使用流程上下文的变量，还可以使用循环上下文的局部变量，例如循环集合中每次循环到的数据对象，或者是循环次数的索引（索引从 `0` 开始计数）。局部变量的作用域仅限于循环内部，如果有多层循环嵌套，可以按层使用具体循环的局部变量。

### 节点配置

![20241016135326](https://static-docs.nocobase.com/20241016135326.png)

#### 循环对象

循环会以循环对象不同数据类型做不同的处理：

1.  **数组**：最常见的情况，通常是可以选择流程上下文的变量，比如查询节点的多条数据结果，或者预加载的对多关系数据。如果选择的是数组，循环节点会遍历数组中的每个元素，每次循环都会将当前元素赋值给循环上下文的局部变量。

2.  **数字**：当选择的变量是一个数字时，会以该数字为循环次数，数字的值仅支持正整数，负数不会进入循环，小数的小数部分会被忽略。局域变量中的循环次数的索引也即循环对象的值。该值以 **0** 为起始，例如循环对象数字为 5 时，每次循环中的对象和索引依次都为：0、1、2、3、4。

3.  **字符串**：当选择的变量是一个字符串时，会以该字符串的长度为循环次数，每次按索引处理字符串中的每一个字符。

4.  **其他**：其他类型的值（包括对象类型）都仅作为单次处理的循环对象，也只会循环一次，通常这种情况不需要使用循环。

除了选择变量，针对数字和字符串类型也可以直接输入常量，例如输入 `5`（数字类型），循环节点会循环 5 次，输入 `abc`（字符串类型），循环节点会循环 3 次，分别处理 `a`、`b`、`c` 三个字符。在选择变量的工具中选择希望使用常量的类型。

#### 循环条件

自版本 `v1.4.0-beta` 起，新增循环条件相关选项，可以在节点配置中开启循环条件。

**条件**

与条件节点中的条件配置类似，可以组合配置，且可以使用当前循环中的变量，如循环对象、循环索引等。

**检查时机**

类似编程语言的 `while` 和 `do/while` 可选择在每次循环开始前，或者每次循环结束后进行配置的条件计算。后置条件计算可以先执行循环体内的其他节点一轮，再进行条件判断。

**不满足条件时**

类似编程语言的 `break` 和 `continue` 语句，可以选择退出循环，或者继续下一轮循环。

#### 循环内部节点出错时的处理

自版本 `v1.4.0-beta` 起，在循环内部节点执行失败时（条件未满足配置、出错等），可以通过配置决定后续流向。支持三种处理方式：

* 退出流程（默认）
* 退出循环并继续流程
* 继续循环下一个循环对象

可根据需要选择使用。

### 示例

例如在订单下单时，需要对订单中的每个商品进行库存检查，如果库存充足则扣减库存，否则订单明细内的商品更新为无效。

1.  创建三张表，商品表 <-(1:m)-- 订单明细表 --(m:1)-> 订单表，数据模型如下：

    | 字段名称     | 字段类型       |
    | ------------ | -------------- |
    | 订单商品明细 | 多对一（明细） |
    | 订单总价     | 数字           |

    | 字段名称 | 字段类型       |
    | -------- | -------------- |
    | 商品     | 一对多（商品） |
    | 数量     | 数字           |

    | 字段名称 | 字段类型 |
    | -------- | -------- |
    | 商品名称 | 单行文本 |
    | 价格     | 数字     |
    | 库存     | 整数     |

2.  创建工作流，触发器选择“数据表事件”，选择“订单”表“新增数据时”触发，并且需要配置上预加载“订单明细”表和明细下的商品表的关系数据：

    ![循环节点_示例_触发器配置](https://static-docs.nocobase.com/0086601c2fc0e17a64d046a4c86b49b7.png)

3.  创建循环节点，选择循环对象为“触发数据 / 订单明细”，即对订单明细表中的每一条数据：

    ![循环节点_示例_循环节点配置](https://static-docs.nocobase.com/2507becc32db5a9a0641c198605a20da.png)

4.  循环节点内部创建一个“条件判断”节点，判断商品的库存是否充足：

    ![循环节点_示例_条件判断节点配置](https://static-docs.nocobase.com/a6d08d15786841e1a3512b38e4629852.png)

5.  如果充足则在“是”的分支中创建一个“计算节点”和一个“更新数据”节点，将计算完扣减的库存更新至对应商品的记录：

    ![循环节点_示例_计算节点配置](https://static-docs.nocobase.com/8df3604c71f8f8705b1552d3ebfe3b50.png)

    ![循环节点_示例_更新库存节点配置](https://static-docs.nocobase.com/2d84baa9b3b01bd85fccda9eec992378.png)

6.  否则在“否”的分支中创建一个“更新数据”节点，更新订单明细的状态为“无效”：

    ![循环节点_示例_更新订单明细节点配置](https://static-docs.nocobase.com/4996613090c254c69a1d80f3b3a7fae2.png)

总的流程结构如下图：

![循环节点_示例_流程结构](https://static-docs.nocobase.com/6f59ef246c1f19976344a7624c4c4151.png)

配置完成并激活该流程后，当创建新订单时，会自动检查订单明细中的商品库存，如果库存充足则扣减库存，否则订单明细内的商品更新为无效（以便计算有效的订单总价）。
