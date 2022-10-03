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

## 平台
包括两种：本地+Github、Overleaf以及两种平台之间的同步方式，请参考[该篇笔记](./Platform.md)。

## 工具

1. [IguanaTex](https://github.com/Jonathan-LeRoux/IguanaTex/blob/v1.60.2/README.md) <span id="IguanaTex"></span>
   
   1. **用途**：用于在ppt中插入LaTeX公式
   
   2. **设置常用模板**：可以将常用的宏设为默认，以符合自己的使用习惯
      
      <div align=center><img src="./images/IguanaTeX.png" alt="image-20220919215903881" style="zoom:50%;" /></div>
   
   3. **Tips**: ctrl+z会回退到上一次编译时的状态，而不是上一次操作，在IguanaTex中要慎用撤回键！

   4. \usepackage[a4paper, total={4.4cm, 4in}]{geometry}

2. 语法检查：[Grammarly](https://app.grammarly.com/), [WordTune](https://app.wordtune.com/)

3. LaTeX OCR [mathpix](https://mathpix.com/)：从图片中识别LaTeX公式，适合与[IguanaTex](#IguanaTex)配合使用。

## LaTeX技巧

1. 如果有很多章节，不同章节使用一个TeX文件单独写，使用input命令插入即可，使得文件的逻辑更加清晰
2. 使用\textbf{xxxx}~~ 可以达到与\paragraph{xxxx}类似的效果，区别在于前者段落间的间距更小，可以在需要节省空间时使用。
3. 当需要插入多幅图片时：

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

4. \setlength\itemsep{0em}

5. \setcounter{AlgoLine}{0}——从1开始

6. \paragraph and \textbf

7. \input

8. command file

9. 更改页面大小：\usepackage[a4paper, total={7cm, 4in}]{geometry}

10. 自定义字体背景色
    
    ```latex
    \usepackage{color,soul} # 相关包
    \definecolor{myYel}{rgb}{1,1,0.69} # 定义颜色 
    \DeclareRobustCommand{\hly}[1]{{\sethlcolor{myYel}\hl{#1}}} # 定义字体背景色命令
    \hly{some information of $f_t$} # 使用
    ```

11. 定义宏：
    
    1. \newcommand\sbr[1]{\left( #1 \right)}
    2. \newcommand\inner[2]{\langle #1, #2 \rangle}



13. 当篇幅不符合要求（过长或过短）
    在overleaf中更换TeX Live版本，有些版本编译出来的篇幅较长、有些较短，这种方法不会影响正文内容的正常显示

14. 文章中引用公式要用\eqref{}而非直接用\ref{}

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

### 图片

1. 插入图片需要使用pdf，否则放大之后会模糊

### 表格

1. 要在图例中对表格的内容充分的解释。
2. 控制表格宽度
3. 控制表格行高
4. \label要在\caption后面，否则虽然不会报错，但实际的编号是错的

### 引用
包括引用规范与常见会议/期刊的引用举例，请参考[该篇笔记](./Reference.md)。

## 写作经验

1. 如果一个大section中只有一个subsection，那么这样的结构就没有必要
2. 涉及到一个符号的时候，要加上一些描述性的信息
3. 如果段落最后一行只有两三个单词，想办法将其缩进上一行
4. 不要用next/last section，直接说 section x.x

## 其他

### 论文匿名化

**匿名化工具**：[Anonymous GitHub](https://anonymous.4open.science/)，用于论文中或者rebuttal期间匿名提交代码/图片等补充材料

**使用**：

1. 访问[Anonymous GitHub](https://anonymous.4open.science/), 利用github账号登录
2. 选择要匿名化的repo
3. 自定义有效期，以及匿名化后的名称
4. 这个网页会自动处理你的仓库，然后替换你填写的需要匿名化的关键字，然后给出一个网页url，就是匿名后的repo地址

## 参考资料

1. [常见符号及其对应的LaTeX表示](./materials/LatexSymbol.pdf)
2. 赵鹏师兄之前做的[相关内容](./materials/LaTeXAcademicWriting.pdf)