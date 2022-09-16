# 写作经验整理

## 语法

1. 行内公式或\emph中的内容最好放在一行，通过换表达方法避免换行
2. i.e.的平替：namely，that is，e.g.的平替：for example
3. equation是“方程”的意思，不要滥用，可以用equality/expression代替
4. e.g.的使用方法：xxxxxxxxxx, e.g., xxxxxxxx
5. However的转折意味很强，一般不轻易用，轻微的转折用nevertheless, but, while替代
6. Method/approach是方法论层面，algorithm是具体实现



## 不同环境

1. 本地+Github
2. overleaf
3. iguanatex



## LaTeX技巧

1. 如果有很多章节，不同章节使用一个TeX文件单独写，使用input命令插入即可，使得文件的逻辑更加清晰
2. 使用\textbf{xxxx}~~ 可以达到与\paragraph{xxxx}类似的效果，区别在于段落间的间距更小，节省空间
3. 当需要插入多幅图片时

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

4. \setlength\itemsep{0em}

5. \setcounter{AlgoLine}{0}——从1开始

6. 定义宏：

   1. \newcommand\sbr[1]{\left( #1 \right)}
   2. \newcommand\inner[2]{\langle #1, #2 \rangle}

   

   

### 图片

### 表格

1. 

## 写作经验

1. 如果一个大section中只有一个subsection，那么这样的结构就没有必要
2. 涉及到一个符号的时候，要加上一些描述性的信息
3. 如果段落最后一行只有两三个单词，想办法将其缩进上一行
4. 不要用next/last section，直接说 section x.x



