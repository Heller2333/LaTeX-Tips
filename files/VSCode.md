# VSCode使用技巧

**配置VSCode的Latex环境**

## VSCode上好用的插件
1. Latex支持插件：LaTeX Workshop
2. Code Spell Checker：语法拼写检查
3. Grammarly: 登录Grammarly账号即可在VSCode本地进行语法检查

**注**：安装插件之后需要重启VSCode。

## Windows
1. [TeX Live 下载与安装](https://tug.org/texlive/acquire-iso.html)
2. 下载安装VScode
3. 安装LaTeX Workshop插件
4. Latex环境配置，参考配置见[该文件](../materials/LaTeX_ENV.md)（可按需修改, 尤其要修改相关路径）



## Mac系统
环境配置请参考[这篇博客](https://mathjiajia.github.io/vscode-and-latex/#step-1-download--install-tex-live)。

### 编译方式
1. **采用何种编译方式**：如果只是对tex文件内容进行了修改而没有修改引用信息，则可以只用```pdfLaTeX```编译一次即可；如果对引用信息进行了修改，则需要使用带```bibtex```的编译方式进行编译。

2. **默认编译方式**：tex源码的编译方式是根据json文件中的顺序决定的。若json文件中对于编译方式（recipe）的描述为：

```json
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
则对tex文件使用ctrl+s时的默认编译方式为```pdfLaTeX```。推荐使用此处的编译顺序。