# 笔记需知

> [!IMPORTANT] 为什么要学习 Markdown
> HTML 太臃肿，PDF 不够灵活，纯文本又丢失了所有结构。
> 
> Markdown 恰好处于最佳平衡点：轻量、通用、结构清晰，人和机器都能轻松阅读。


- ​vscode安装插件：GitHub Markdown Preview
- 学习markdown：
  - https://docs.github.com/zh/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github
  - https://docs.github.com/zh/get-started/writing-on-github/working-with-advanced-formatting


## markdown文件

!!! note https://squidfunk.github.io/mkdocs-material/reference/admonitions/

    !!! note        备注/补充说明
    !!! abstract    摘要/概述
    !!! info        一般信息
    !!! example     示例/演示
    !!! tip         技巧/建议
    !!! success     成功/完成提示
    !!! question    问题/待解答
    !!! warning     警告/注意事项
    !!! failure     失败/错误提示
    !!! danger      危险/严重警告
    !!! bug         Bug 报告
    !!! quote       引用

    !!! note ""
        Removing the title

> [!NOTE]
> Useful information that users should know, even when skimming content.

> [!TIP]
> Helpful advice for doing things better or more easily.

> [!IMPORTANT]
> Key information users need to know to achieve their goal.

> [!WARNING]
> Urgent info that needs immediate user attention to avoid problems.

> [!CAUTION]
> Advises about risks or negative outcomes of certain actions.

### 希腊字母

希腊字母在科学、数学、工程等领域中广泛使用，Unicode 为它们分配了专门的代码点。

### Emoji编码

彩色表情符号（Emoji）是 Unicode 标准中定义的字符（如 😊、🚀、🌟），大部分现代系统（Windows/macOS/Linux）、编辑器（VS Code/Typora）和平台（GitHub/语雀/Notion）均支持直接显示彩色 Emoji。输入 Emoji 本质是输入对应的 Unicode 字符。

😊 👍 🚀 🌟 🔴 🟢 🟡 ❤️ ✨ 🎉 📚 💻 🌍 🦜 🐧 🦁 🐘 🦉 🍎 🍕 🚗 ✈️ 🏠 🌳 🌊 ☀️ 🌙 ⭐ 💡 ❗ 🔔 📌 🔑 💼 🎯 🏆 🎈

部分 Markdown 平台（如 GitHub、GitLab、Discord）支持用 :别名:​ 格式输入 Emoji（本质是平台内置别名映射，自动转换为 Emoji 字符）。
- `:+1:`👍
- `:smile:`😊
- `:rocket:`🚀
- `:star:`⭐
- `:heart:`❤️
- `:fire:`🔥
- `:warning:`⚠️
- `:bulb:`💡
- `:earth_africa:`🌍
- `:computer:`💻

### 公式

### mermaid

## 程序员修炼之道3

“Keep Knowledge in Pain Text（用纯文本保存知识）”

纯文本的威力：
优点：
保证不过时：纯文本是人类可直接阅读和理解的形式，只要人们能够理解文本的格式，就可以对其进行解析，相比二进制文件更具持久性。比如 HTML、XML 等都是常见的纯文本语言，即使未来软件和系统不断更新换代，纯文本依然能够被读取和处理。
杠杆作用：计算世界中的各种工具，从源码管理系统到编译环境、编译器及独立的过滤器等，都能对纯文本进行操作。这意味着纯文本可以与各种工具良好地协同工作，方便程序员进行代码的编写、管理和处理。
更易于测试：用纯文本创建用于驱动系统测试的合成数据非常方便，增加、更新或修改测试数据也比较简单，无需为此创建特殊工具。这使得测试过程更加高效和便捷，有助于提高代码的质量和可靠性。
缺点：与压缩的二进制格式相比，存储纯文本需要更多的空间；解释及处理纯文本文件，在计算上的代价可能更昂贵。
