# 写作经验整理

## LaTeX简介

### LaTeX文件类型

1. tex文件 

2. sty文件

3. bib文件
   
## 语法

4. 行内公式或\emph中的内容最好放在一行，通过换表达方法避免换行

5. i.e.的平替：namely，that is，e.g.的平替：for example

6. equation是“方程”的意思，不要滥用，可以用equality/expression代替

7. e.g.的使用方法：xxxxxxxxxx, e.g., xxxxxxxx

8. However的转折意味很强，一般不轻易用，轻微的转折用nevertheless, but, while替代

9. Method/approach是方法论层面，algorithm是具体实现

10. TODO

## 平台
请参考[该篇笔记](./files/Platform.md)，包括：
1. 两类编译平台：本地+Github、Overleaf
2. 两种平台之间的同步方式

## 工具

1. [IguanaTex](https://github.com/Jonathan-LeRoux/IguanaTex/blob/v1.60.2/README.md) <span id="IguanaTex"></span>
   
   1. **用途**：用于在ppt中插入LaTeX公式
   
   2. **设置常用模板**：可以将常用的宏设为默认，以符合自己的使用习惯
      
      <div align=center><img src="./images/IguanaTeX.png" alt="image-20220919215903881" style="zoom:50%;" /></div>
   
   3. **慎用ctrl+z撤回**: ctrl+z会回退到上一次编译时的状态，而不是上一次操作，在IguanaTex中要慎用撤回键！

   4. **设置页面宽度**：```\usepackage[a4paper, total={4.4cm, 4in}]{geometry}```，更改其中```4cm```参数调整宽度

   5. **设置行距**：
   ```latex
      \usepackage{setspace}
      \linespread{1.5} % 1.5倍行距
   ```

   6. **快速查看LaTeX源码**：每次都点击'Edit LaTeX display'打开IguanaTex编辑界面查看源码过于繁琐。可以按照如下方式操作：
        1. 在公式上右键，选择`View Alt Text`
        <div align=center><img src="https://github.com/Heller2333/LaTeX-Tips/raw/main/images/IguanaTex-2.png" style="zoom:50%;" /></div>

        2. 之后即可在右侧工具栏直接查看LaTeX源码 
        <div align=center><img src="https://github.com/Heller2333/LaTeX-Tips/raw/main/images/IguanaTex-3.png" style="zoom:50%;" /></div>


2. **语法检查**：[Grammarly](https://app.grammarly.com/), [WordTune](https://app.wordtune.com/)
    1. Grammarly插件：VSCode

3. [Mathpix](https://mathpix.com/)
    1. 用途：LaTeX OCR——从图片中识别LaTeX公式，适合与[IguanaTex](#IguanaTex)配合使用。

## LaTeX技巧

1. 如果有很多章节，不同章节使用一个TeX文件单独写，使用input命令插入即可，使得文件的逻辑更加清晰
2. 使用```\textbf{}~~```可以达到与```\paragraph{}```类似的效果，区别在于前者段落间的间距更小，可以在需要节省空间时使用。

4. \setlength\itemsep{0em}

5. \setcounter{AlgoLine}{0}——从1开始

7. \input

10. 自定义字体背景色
    
    ```latex
    \usepackage{color,soul} # 相关包
    \definecolor{myYel}{rgb}{1,1,0.69} # 定义颜色 
    \DeclareRobustCommand{\hly}[1]{{\sethlcolor{myYel}\hl{#1}}} # 定义字体背景色命令
    \hly{some information of $f_t$} # 使用
    ```

13. 当篇幅不符合要求（过长或过短）
    在overleaf中更换TeX Live版本，有些版本编译出来的篇幅较长、有些较短，这种方法不会影响正文内容的正常显示

14. 文章中引用公式要用\eqre„f{}而非直接用\ref{}

16. 竖线的使用
* 集合里用\mid，例如
  
  ```latex
  ${x \mid \norm{x}_2 \geq 1}$
  ```
* 条件概率用\given，定义如下
  
  ```latex
  \newcommand\given[1][]{\:#1\vert\:}
  \newcommand\givenn[1][]{\:#1\middle\vert\:}
  ```
17. 示性函数用如下定义，不要用\mathbb{I}
    
    ```latex
    \def \indicator {\mathbbm{1}}
    ```

18. TODO

### 图片

1. 插入图片需要使用pdf，否则放大之后会模糊
2. 当需要插入多幅图片时：
```latex
\begin{figure*}[!t]
  \centering
  \subfigure[nameA]{ 
      \label{fig:nameA} 
      \includegraphics[clip, trim=xcm xcm xcm xcm,width=0.3\textwidth]{nameA.pdf}}       
      \hspace{3mm}
  \subfigure[nameB]{ 
      \label{fig:nameB}
      \includegraphics[clip, trim=xcm xcm xcm xcm, width=0.3\textwidth]{nameB.pdf}}  
      \hspace{3mm}   
  \subfigure[nameC]{ 
      \label{fig:nameC}
      \includegraphics[clip, trim=xcm xcm xcm xcm, width=0.3\textwidth]{nameC.pdf}}
  \caption{My caption.}
  \label{fig:xxx}
\end{figure*}
```
其中trim的4个参数分别代表左下右上 

注：如果遇到 "Missing number, treated as zero" 错误，则可能是因为subfigure缺少宽度数值导致，解决方案：

```latex
\begin{figure*}[!t]
  \centering
  \begin{subfigure}[b]{\textwidth}{ 
      \label{fig:nameA} 
      \includegraphics[clip, trim=xcm xcm xcm xcm,width=0.3\textwidth]{nameA.pdf}}       
      \hspace{3mm}
  \end{subfigure}
\end{figure*}
```

3. TODO

### 表格

1. 要在图例中对表格的内容充分的解释。
2. 控制表格宽度
3. 控制表格行高
4. ```\label```要在```\caption```后面，否则虽然不会报错，但实际的编号是错的
5. TODO

### 算法
请参考[该篇笔记](./files/algo.md)，包括：
1. 不同算法包的区别
2. 如何引用算法特定行

### 引用
请参考[该篇笔记](./files/Reference.md)，包括：
1. 引用规范
2. 常见会议/期刊的引用举例

### 宏
将常用符号以及操作符定义为宏，请参考[该文件](./files/macros.md)。

### 多文件编译
常用于投稿时产生正文与附录，假设正文位于```main.tex```中，附录位于```supp.tex```中 ：
1. **作为同一个文件编译**：使用```\input```命令在正文末尾插入：
```latex
\bibliography{xxx} % bib文件

% 添加附录，使用\input命令将supp.tex中的内容加入
\newpage
\appendix
\input{supp}

\end{document}
```
```\input```命令的本质是粘贴，```supp.tex```中不需要有完整的文件结构，只需要有LaTeX代码片段即可。进行编译时只需要编译```main.tex```文件即可。

2. **作为不同文件编译**：核心问题在于跨文件引用公式、定理等。具体做法为在```main.tex```开头加入
```latex
\usepackage{xr}
\externaldocument{supp}
```
在```supp.tex```开头加入
```latex
\usepackage{xr}
\externaldocument{main}
```
之后即可跨文件引用公式、定理等。进行编译时需要分别编译```main.tex```以及```supp.tex```。

定理序号衔接：使用setcounter命令——TODO

## 写作经验

1. 如果一个大section中只有一个subsection，那么这样的结构就没有必要
2. 涉及到一个符号的时候，要加上一些描述性的信息
3. 如果段落最后一行只有两三个单词，想办法将其缩进上一行
4. 不要用next/last section，直接说 section x.x
5. TODO

## 其他

### 论文匿名化

**匿名化工具**：[Anonymous GitHub](https://anonymous.4open.science/)，用于论文中或者rebuttal期间匿名提交代码/图片等补充材料

**使用**：
1. 访问[Anonymous GitHub](https://anonymous.4open.science/), 利用github账号登录
2. 选择要匿名化的repo
3. 自定义有效期，以及匿名化后的名称
4. 这个网页会自动处理你的仓库，然后替换你填写的需要匿名化的关键字，然后给出一个网页url，就是匿名后的repo地址

### Beamer
使用LaTeX制作ppt
TODO

### 获取arXiv源码


## 参考资料

1. [常见符号及其对应的LaTeX表示](./materials/LatexSymbol.pdf)
2. [Word/Powerpoint中的LaTeX写法](./materials/WordLatex.pdf)
3. 赵鹏师兄之前做的[相关内容](./materials/LaTeXAcademicWriting.pdf)