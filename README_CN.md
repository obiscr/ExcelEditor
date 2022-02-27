# ExcelEditor

[![Version](https://img.shields.io/jetbrains/plugin/v/18663-exceleditor.svg)](https://plugins.jetbrains.com/plugin/18663-exceleditor)
[![Downloads](https://img.shields.io/jetbrains/plugin/d/18663-exceleditor.svg)](https://plugins.jetbrains.com/plugin/18663-exceleditor)
[![Slack](https://img.shields.io/badge/Slack-%23ExcelEditor-blue?logo=Slack)](https://observercreator.slack.com/)

<p> 

[简体中文](https://github.com/obiscr/ExcelReader/blob/main/README_CN.md)  |
[English](https://github.com/obiscr/ExcelEditor/blob/main/README.md)

</p>

这款插件是 [**ExcelReader**](https://plugins.jetbrains.com/plugin/14722-excelreader)
的增强版。

具有所有ExcelReader插件的功能，并提供了：

+ 打开多个文件 (支持相同名字的Excel文件)
+ 数据修改
+ 文件对比
+ Excel文件合并

**Note** : 对于特别重要的数据，建议使用
专业的 Excel 工具进行修改和合并。 如果你想使用这个工具
要修改或合并重要数据，请务必在执行此操作之前备份您的数据。

![支持相同名字](https://obiscr.github.io/docs/ExcelEditor/images/SupportSameName.gif)

![文件杜比](https://obiscr.github.io/docs/ExcelEditor/images/FileMerge.gif)

## 安装

- 使用内置插件系统:

  <kbd>Settings/Preferences</kbd> > <kbd>Plugins</kbd> > <kbd>Marketplace</kbd> > <kbd>Search for "ExcelEditor"</kbd> >
  <kbd>Install Plugin</kbd>

## 注意

如果您在之前已经安装了 [ExcelReader](https://plugins.jetbrains.com/plugin/14722-excelreader) ,
那么当你安装ExcelEditor的时候需要卸载或者禁用ExcelReader. 他们两者不能同时启用。

安装ExcelEditor之后，当你启动IDE的时候，可能会看到如下提示:

![插件自动检查](https://raw.githubusercontent.com/obiscr/docs/gh-pages/ExcelEditor/images/Plugin_Auto_Check.png)

此时，选择 **Use ExcelEditor by obiscr**。


# 数据修改

通常有三种数据格式: **日期格式**, **普通文本**, 和 **公式**.

## 日期格式

修改日期格式时：写入的新值必须符合标准日期格式，否则写入失败，恢复原值。 那就是：编辑不成功。

![修改日期](https://user-images.githubusercontent.com/28687074/154837396-91fe23ab-1e81-41c6-9490-2ab956984784.gif)

## 普通文本
可以直接写入普通文本数据。

## 公式
对于公式，修改会触发重新计算，最终值是工具公式计算出来的值，而不是实际写入的值。

例如:
单元格 **A1** 的值是: `256`, 单元格 **A2** 的值是 `512`, 单元格 **A3** 的类型是公式: `SUM(A1:A2)`. 正常情况下, 单元格 **A3** 的值是: 768。

此时，我们将单元格A3的值修改为1000，这将触发公式重新计算。
也就是说，在不修改单元格A1和单元格A2的情况下，单元格A3的计算结果仍然是768。
**假设您在修改单元格 A3 之前将单元格 A1 修改为 1000，那么当您修改单元格 A3 时,
计算的值应该是: 1512, 因为 A3(1512) = A1(1000) + A2(512)**。

![修改公式](https://user-images.githubusercontent.com/28687074/154837384-94199813-e7a9-4819-80fd-6890333b4d19.gif)

# 文件对比
csv文件只能和csv文件比较，xls文件和xlsx文件可以任意相互比较

# Excel合并
Excel合并有三种格式: **合并单行**, **合并多行**, **合并所有行**。

数据写入规则：如果要将左侧的数据写入到右侧，点击 ![](https://intellij-icons.jetbrains.design/icons/AllIcons/vcs/arrow_right.svg). 反过来，如果你想把右边的数据写到左边，点击 ![](https://intellij-icons.jetbrains.design/icons/AllIcons/vcs/arrow_left.svg)。箭头的方向形象地说明了数据的方向。

## 合并单行
要合并单行，只需单击当前行的 ![](https://intellij-icons.jetbrains.design/icons/AllIcons/vcs/arrow_right.svg) 或者 ![](https://intellij-icons.jetbrains.design/icons/AllIcons/vcs/arrow_left.svg) 。

## 合并多行
要合并多行，只需选择左侧或右侧的数据，然后单击工具栏上的合并按钮。

## 合并所有行
要合并所有行，只需单击工具栏上的合并按钮即可合并。
但是不能在操作前选择多行数据。
也就是说，如果选择多行（选择的行数大于1行），
它将作为多行合并处理，并非所有行都会被合并。

![文件合并](https://obiscr.github.io/docs/ExcelEditor/images/FileMerge.gif)

# 贡献

请fork此仓库提交PR或者创建issue进行反馈。也可以加入[Slack](https://observercreator.slack.com/)。

> 值得一提的是，与 ExcelReader 不同，ExcelEditor 的 [Slack](https://observercreator.slack.com/) 只用于问题反馈等等。ExcelEditor是不开源的。
