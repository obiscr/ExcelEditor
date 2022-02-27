# ExcelEditor

<p> 

[简体中文](https://github.com/obiscr/ExcelEditor/blob/main/README_CN.md)  |
[English](https://github.com/obiscr/ExcelEditor/blob/main/README.md)

</p>

<!-- Plugin description -->

[![Version](https://img.shields.io/jetbrains/plugin/v/18663-exceleditor.svg)](https://plugins.jetbrains.com/plugin/18663-exceleditor)
[![Downloads](https://img.shields.io/jetbrains/plugin/d/18663-exceleditor.svg)](https://plugins.jetbrains.com/plugin/18663-exceleditor)
[![Slack](https://img.shields.io/badge/Slack-%23ExcelEditor-blue?logo=Slack)](https://observercreator.slack.com/)


This plugin is an Enhanced Edition of [**ExcelReader**](https://plugins.jetbrains.com/plugin/14722-excelreader).
Has all the features of ExcelReader. And additionally provides:

+ Open multiple files (supports Excel files with the same name)
+ Data modification
+ File comparison
+ Excel Merge Function

For more details, please see the [document](https://obiscr.github.io/docs/ExcelEditor)

**Note** : For particularly important data, it is recommended to use 
professional Excel tools to modify and merge. If you want to use this tool 
to modify or merge important data, be sure to back up your data before doing so.
<!-- Plugin description end -->

![Image_Multi_Sheet.gif](https://obiscr.oss-cn-hongkong.aliyuncs.com/res/ExcelReader/docs/Image_Multi_Sheet.gif?versionId=CAEQUBiBgIDR2YK6yBciIDZlODBlNjA4NmNlZDQyYTdiZmY0OWRiYzg2ZTA0MTE2)

![Image_CSV](https://obiscr.oss-cn-hongkong.aliyuncs.com/res/ExcelReader/docs/Image_CSV.png?versionId=CAEQUBiBgMCkvJK6yBciIDllYjgxNDk5Y2YyZjQ1ZWU4M2VjMjY3NjVhNjBlYTBh)

![Image_XLS](https://obiscr.oss-cn-hongkong.aliyuncs.com/res/ExcelReader/docs/Image_XLS.png?versionId=CAEQUBiBgMCdvJK6yBciIDFlZGVjNzcwZmEzYzRkN2JiMzE0N2Y1ZGQ5NTllMDFk)

![Image_XLSX](https://obiscr.oss-cn-hongkong.aliyuncs.com/res/ExcelReader/docs/Image_XLSX.png?versionId=CAEQUBiBgICPvJK6yBciIGI0MGI5MGU1MGVhYzQxMzJhZmY2NWU4ZWNmNmRhNGQ2)

![Dark_Model](https://obiscr.oss-cn-hongkong.aliyuncs.com/res/ExcelReader/docs/Dark_Model.png?versionId=CAEQUBiBgICWvJK6yBciIDljNmYwZDY1YmRkYjQwZThiZDFkNjc4MTIxYzBhOTk0)

# 安装
### 在IDE里面进行安装
打开 "File" - “Settings” - “Plugins”，选择 “Marketplace”，输入 `ExcelReader` ，点击 `install` 即可安装到IDE。
> 不同版本的IDE，上述的打开方式可能略有差别

### 通过 WEB 安装
[点击前往ExcelEditor插件主页](https://plugins.jetbrains.com/plugin/14722-excelreader)

# 使用
选中一个后缀是 `.xls` 或 `.xlsx` 或 `.csv` 的文件，鼠标右击选择最上面 `Open As ExcelReader` 即可打开。
ExcelReader 同时支持快捷键打开，选中文件后，按下对应的快捷键即可打开。不同的平台快捷键略有差异。

> 在 Windows 或者 Linux 平台
+ Ctrl Shift D

> 在 macOS 平台
+ Command Shift D

打开一个文件之后，ExcelReader界面最上面可以进行简单的搜索操作。

选择 `All Column`，是在所有列中搜索；选择某个具体的列，则只在选择的列中进行搜索。

# 贡献

如果您喜欢这款插件，并且有意加入到开发工作中来，请fork此仓库提交PR或者创建issue进行反馈。

# 感谢

+ [Apache](https://poi.apache.org/)
+ [hutool](https://www.hutool.cn/)
+ [JetBrains](https://www.jetbrains.com)
=======
**Note** : For particularly important data, it is recommended to use
professional Excel tools to modify and merge. If you want to use this tool
to modify or merge important data, be sure to back up your data before doing so.

![SupportSameName](https://obiscr.github.io/docs/ExcelEditor/images/SupportSameName.gif)

![FileMerge](https://obiscr.github.io/docs/ExcelEditor/images/FileMerge.gif)

## Installtion

- Using IDE built-in plugin system:

  <kbd>Settings/Preferences</kbd> > <kbd>Plugins</kbd> > <kbd>Marketplace</kbd> > <kbd>Search for "ExcelEditor"</kbd> >
  <kbd>Install Plugin</kbd>

## Notice

If you have installed the [ExcelReader](https://plugins.jetbrains.com/plugin/14722-excelreader) plugin before, ExcelReader can be uninstalled or disabled 
when you purchase ExcelEditor. Both of them cannot be enabled at the same time.

Maybe you will get a prompt like the following when you start the IDE:

![Plugin_Auto_Check](https://raw.githubusercontent.com/obiscr/docs/gh-pages/ExcelEditor/images/Plugin_Auto_Check.png)

At this point, choose to **Use ExcelEditor by obiscr**.


# Data modification
There are generally three formats of data: **Date Format**, **Normal Text**, and **Formula**.

## Date Format
When modifying the date format: the new value written must conform to the standard date format, otherwise the writing will fail and the original value will be restored. That is: the edit was unsuccessful.

![DescEditDate](https://user-images.githubusercontent.com/28687074/154837396-91fe23ab-1e81-41c6-9490-2ab956984784.gif)

## Normal Text
Normal text data can be written directly.

## Formula
For formulas, modification will trigger recalculation, and the final value is the value calculated by the tool formula, not the actual written value.

For example:
The value of cell **A1** is: `256`, the value of cell **A2** is `512`, the type of cell **A3** is the formula: `SUM(A1:A2)`. Under normal circumstances, the value of cell **A3** is: 768.

At this point, we modify the value of cell A3 to 1000, which will trigger the formula to recalculate. 
That is to say, without modifying cell A1 and cell A2, the calculated result of cell A3 is still 768.
**Suppose you modify cell A1 to 1000 before modifying cell A3, then when you modify cell A3, 
the calculated value should be: 1512, because A3(1512) = A1(1000) + A2(512)**.

![DescEditFormula](https://user-images.githubusercontent.com/28687074/154837384-94199813-e7a9-4819-80fd-6890333b4d19.gif)

# File comparison
The csv files can only be compared with csv files, xls files and xlsx files can be compared with each other arbitrarily

# Excel Merge Function
File Merge supports three modes: **Merge Single Row**, **Merge Multiple Rows**, **Merge All Rows**.

Data writing rules: If you want to write the data on the left to the right, click ![](https://intellij-icons.jetbrains.design/icons/AllIcons/vcs/arrow_right.svg). In turn, if you want to write the data on the right to the left, click ![](https://intellij-icons.jetbrains.design/icons/AllIcons/vcs/arrow_left.svg). The direction of the arrow vividly illustrates the direction of the data.

## Merge Single Row
To merge a single line, you only need to click the ![](https://intellij-icons.jetbrains.design/icons/AllIcons/vcs/arrow_right.svg) or ![](https://intellij-icons.jetbrains.design/icons/AllIcons/vcs/arrow_left.svg) of the current line.

## Merge Multiple Rows
To merge the selected rows, just select the data on the left or right and click the merge button on the toolbar.

## Merge All Rows
To merge all rows, simply click the merge button on the toolbar to merge. 
But you cannot select multiple rows of data before the operation.
That is to say, if you select multiple rows (the number of selected rows is greater than 1 row), 
it will be processed as multi-row merge, and not all rows will be merged.

![FileMerge](https://obiscr.github.io/docs/ExcelEditor/images/FileMerge.gif)

# Contribution

Please fork this repository and submit a PR or create an issue for feedback. Also join [Slack](https://observercreator.slack.com/).

> It is worth mentioning that, unlike ExcelReader, ExcelEditor's [Slack](https://observercreator.slack.com/) is only used for problem feedback and so on. ExcelEditor is not open source.
