# ExcelEditor

<p> 

[简体中文](https://github.com/obiscr/ExcelEditor/blob/main/README_CN.md)  |
[English](https://github.com/obiscr/ExcelEditor/blob/main/README.md)

</p>

<!-- Plugin description -->

[![Version](https://img.shields.io/jetbrains/plugin/v/18663-exceleditor.svg)](https://plugins.jetbrains.com/plugin/18663-exceleditor)
[![Downloads](https://img.shields.io/jetbrains/plugin/d/18663-exceleditor.svg)](https://plugins.jetbrains.com/plugin/18663-exceleditor)
[![Slack](https://img.shields.io/badge/Slack-%23ExcelEditor-blue?logo=Slack)](https://join.slack.com/t/observercreator/shared_invite/zt-14g3dnzkx-FGJM_WgY~vj0bJINTHQSAA)


# 折扣 (Discount)

Add a WeChat group or join Slack for a discount

+ Slack

  [Click to Join Slack](https://join.slack.com/t/observercreator/shared_invite/zt-14g3dnzkx-FGJM_WgY~vj0bJINTHQSAA)

+ 微信群

  <img width=200 src="https://user-images.githubusercontent.com/28687074/188489998-9fee38f5-5183-4e4a-aa7f-c5d31074dcc6.png" alt="二维码">


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

Please fork this repository and submit a PR or create an issue for feedback. Also join [Slack](https://join.slack.com/t/observercreator/shared_invite/zt-14g3dnzkx-FGJM_WgY~vj0bJINTHQSAA).

> It is worth mentioning that, unlike ExcelReader, ExcelEditor's [Slack](https://join.slack.com/t/observercreator/shared_invite/zt-14g3dnzkx-FGJM_WgY~vj0bJINTHQSAA) is only used for problem feedback and so on. ExcelEditor is not open source.
