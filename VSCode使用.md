# VSCode使用技巧

**配置VSCode的Latex环境**

## VSCode上好用的插件
1. Code Spell Checker：语法拼写检查
2. Grammarly: 登录Grammarly账号即可在VSCode本地进行语法检查

## Windows@baiy

## Mac系统
环境配置请参考[这篇博客](https://mathjiajia.github.io/vscode-and-latex/#step-1-download--install-tex-live)。

### 编译方式
1. **采用何种编译方式**：如果只是对tex文件内容进行了修改而没有修改引用信息，则可以只用pdfLaTeX编译一次即可；如果对引用信息进行了修改，则需要使用带bibtex的编译方式进行编译。

2. **默认编译方式**：tex源码的编译方式是根据json文件中的顺序决定的。若json文件中对于编译方式（recipe）的描述为：

```latex
"latex-workshop.latex.recipes": [
 {
  "name": "pdfLaTeX",
  "tools": [
   "pdflatex"
  ]
 },
 {
  "name": "xelatex",
  "tools": [
   "xelatex"
  ]
 },
 {
  "name": "pdflatex ➞ bibtex ➞ pdflatex`×2",
  "tools": [
   "pdflatex",
   "bibtex",
   "pdflatex",
   "pdflatex"
  ]
 },
 {
 "name": "xelatex ➞ bibtex ➞ xelatex`×2",
 "tools": [
   "xelatex",
   "bibtex",
   "xelatex",
   "xelatex"
  ]
 }
]
```
则对tex文件使用ctrl+s时的默认编译方式为pdfLaTeX。推荐使用此处的编译顺序。