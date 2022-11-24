<script>
    locker("Youths");
</script>
# 青松助手

## 声明、协议及警告

以下程序仅用于提高生产力，不得用于任何违法违纪或违规之用途；违者自行承担全部责任，自行为自己的前途负责。在下载或使用以下程序前，你还需阅读并同意该[许可协议](page/right)。

以下程序如有疏漏或不足之处，欢迎交流。

## 程序说明

“青松助手”旨在让本学院的青年大学习统计实现半自动化，从而避免大部分重复性劳动，让数据的复制不再是统计人员的烦心事。

~~由于作者不具备使用 `C/C++` 实现 `xlsx` 文件读写的能力，~~该程序使用 `Python` 构建。

## 使用方法

1. 首次使用时，应先在下一节的链接中下载青松助手和模板表格。其中模板表格的名字应该是 `model.xlsx`。

2. 从网页入口导出并下载本次需统计的数据，并确保文件名为 `学习组织汇总.xlsx`；随后将 `model.xlsx` 和 `学习组织汇总.xlsx` 两个文件都放置在 `D` 盘根目录（即 `D:\`）下。

3. 运行青松助手。如果你未更改过它的名字，它应该是 `Automation.exe`。如果运行成功，则它应弹出窗口，并在其中输出类似如下的信息：

   ```
   openpyxl\styles\stylesheet.py:226: UserWarning: Workbook contains no default style, apply openpyxl's default
   Automation.py:6: DeprecationWarning: Call to deprecated function get_sheet_by_name (Use wb[sheetname]).
   Automation.py:8: DeprecationWarning: Call to deprecated function get_sheet_by_name (Use wb[sheetname]).
   计算机学院博士生团支部  done!
   2022级研究生四班团支部  done!
   ……
   计算机学院2021级第七团支部      done!
   2020级计算机计算机金融团支部    done!
   处理完成。文件应已存放至D:\x年y月z日青年大学习统计-a时b分c秒.xlsx
   文件D:\学习组织汇总.xlsx应已移除。
   请输入Automation以退出程序；或者直接关闭此窗口：
   ```

   随后，你只需输入 `Automation` 或直接关闭此窗口以退出程序。此时，`D` 盘根目录下的 `学习组织汇总.xlsx` 应该已被删除，且新生成的 `x年y月z日青年大学习统计-a时b分c秒.xlsx.xlsx` 将按格式完成命名，并存有已经统计完成的表格。

4. 以后使用时，只需重复2-3步即可。

## 下载地址

你可以在这里下载<a href="https://raw.githubusercontent.com/BranchGleaner/site/main/docs/gadgets/Automation.exe" target="_blank">青松助手</a>和<a href="https://raw.githubusercontent.com/BranchGleaner/site/main/docs/gadgets/model.xlsx" target="_blank">模板表格</a>。祝使用愉快！

## Q&A

1. 为什么使用时会报错，达不到预期的效果？

   这很可能是因为文件名或文件位置不符合要求。请严格执行使用方法中的操作步骤。如果确定问题不是由此导致的，请检查两个 `xlsx` 文件中工作表的名称。在 `model.xlsx` 中，工作表的名字应该是 `Sheet1`；在 `学习组织汇总.xlsx` 中，工作表的名字应该是 `计算机学院团委`。

2. 为什么我电脑里的文件叫做 `model` 而不是 `model.xlsx`（`学习组织汇总.xlsx` 和 `Automation.exe` 同理）？

   这是由于你的电脑隐藏了文件扩展名。这不会对程序的运行结果产生影响。

3. 为什么我电脑上的杀毒软件/电脑管家提示不安全，甚至报毒？

   作者保证程序不含恶意代码。若出现以上情况，你可以放心地忽略该提示，并将青松助手加入信任区。但若你仍有顾虑，也可以不使用该程序，并从你的电脑上删除它。

4. 为什么我各种方法都试过了，死活使用不了？

   ~~这可能是因为你和它没有缘分或八字不合。~~若出现以上情况，可以与作者反馈或交流。但是请注意：作者不保证修复程序的bug。













