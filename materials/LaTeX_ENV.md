# LaTeX环境配置
```json
{
     // ======================== LaTeX 设置 BEGIN  ========================
        // bibtex 格式
        "latex-workshop.bibtex-format.tab": "tab",
    
        // 自动编译，全部关闭，当且仅当你认为有需要的时候才会去做编译
        "latex-workshop.latex.autoBuild.run": "onSave",
        "latex-workshop.latex.autoBuild.cleanAndRetry.enabled": true,
    
        // 设置 latex-workshop 的 PDF　预览程序，external　指的是外部程序
        "latex-workshop.view.pdf.viewer": "external",
        "latex-workshop.view.pdf.ref.viewer": "external",
        "latex-workshop.view.pdf.external.viewer.command": "C:/Users/Giggle/AppData/Local/SumatraPDF/SumatraPDF.exe",
        "latex-workshop.view.pdf.external.viewer.args": [
            "%PDF%"
        ],
    
        // 配置正向、反向搜索：.tex -> .pdf
        "latex-workshop.view.pdf.external.synctex.command": "C:/Users/Giggle/AppData/Local/SumatraPDF/SumatraPDF.exe",
        "latex-workshop.view.pdf.external.synctex.args": [
            // 正向搜索
            "-forward-search",
            "%TEX%",
            "%LINE%",
            "-reuse-instance",
            // 反向搜索
            "-inverse-search",
            "\"D:/Users/Giggle/AppData/Local/Programs/Microsoft VS Code/Code.exe\" \"D:/Users/Giggle/AppData/Local/Programs/Microsoft VS Code/resources/app/out/cli.js\" -gr %f:%l",
            "%PDF%"
        ],
    
        // 这是一些独立的编译选项，可以作为工具被编译方案调用
        "latex-workshop.latex.tools": [
            {
                // Windows 原生安装 TeX Live 2020 的编译选项
                "name": "Windows XeLaTeX",
                "command": "xelatex",
                "args": [
                    "-synctex=1",
                    "-interaction=nonstopmode",
                    "-file-line-error",
                    "-pdf",
                    "%DOCFILE%"
                ]
            },
            {
                // Windows Biber 编译
                "name": "Windows Biber",
                "command": "biber",
                "args": [
                    "%DOCFILE%"
                ]
            },
            {
                // bibtex
                "name": "bibtex",
                "command": "bibtex",
                "args": [
                  "%DOCFILE%"
                ]
            },
            {
                // bibtex-appendix
                "name": "bibtexapp",
                "command": "bibtex",
                "args": [
                  "appendix"
                ]
            },
            {
                // WSL XeLaTeX 编译一般的含有中文字符的文档
                "name": "WSL XeLaTeX",
                "command": "wsl",
                "args": [
                    "/usr/local/texlive/2020/bin/x86_64-linux/xelatex",
                    "-synctex=1",
                    "-interaction=nonstopmode",
                    "-file-line-error",
                    "-pdf",
                    //"-output-directory=%OUTDIR%",
                    //"-aux-directory=%OUTDIR%",
                    "%DOCFILE%"
                ]
            },
            {
                // WSL biber / bibtex 编译带有 citation 标记项目的文档
                "name": "WSL Biber",
                "command": "wsl",
                "args": [
                    "/usr/local/texlive/2020/bin/x86_64-linux/biber",
                    "%DOCFILE%"
                ]
            },
            {
                // macOS 或者 Linux 的简单编译
                // 两种操作系统的操作方式相同
                "name": "macOS / Linux XeLaTeX",
                "commmand": "xelatex",
                "args": [
                    "-synctex=1",
                    "-interaction=nonstopmode",
                    "-file-line-error",
                    "-pdf",
                    "%DOCFILE%"
                ]
            },
            {
                // macOS 或者 Linux 的索引编译
                // 两种操作系统的操作方式相同
                "name": "macOS / Linux Biber",
                "command": "biber",
                "args": [
                    "%DOCFILE%"
                ]
            },
            {
                "name": "pdflatex",
                "command": "pdflatex",
                "args": [
                    "-synctex=1",
                    "-interaction=nonstopmode",
                    "-file-line-error",
                    "%DOCFILE%"
                ]
            },
        ],
    
        // 这是一些编译方案，会出现在 GUI 菜单里
        "latex-workshop.latex.recipes": [
            {
                "name": "pdflatex",
                "tools": [
                    "pdflatex"
                ]
            },
            {
                // 1.1 Windows 编译简单的小文档，这个选项不太常用，因为绝大多数文章都需要有参考文献索引
                "name": "Windows XeLaTeX 简单编译",
                "tools": [
                    "Windows XeLaTeX"
                ]
            },
            {
                // 1.2 Windows 编译带有索引的论文，需要进行四次编译；-> 符号只是一种标记而已，没有程序上的意义
                "name": "Windows xe->bib->xe->xe 复杂编译",
                "tools": [
                    "Windows XeLaTeX",
                    // "Windows Biber",
                    "bibtex",
                    "Windows XeLaTeX",
                    "Windows XeLaTeX"
                ]
            },
           
            {
                "name": "pdf->bib->pdf->pdf",
                "tools": [
                    "pdflatex",
                    "bibtex",
                    "pdflatex",
                    "pdflatex"
                ]
            },

            {
                "name": "pdf->bib->bib->pdf->pdf",
                "tools": [
                    "pdflatex",
                    "bibtex",
                    "bibtexapp",
                    "pdflatex",
                    "pdflatex"
                ]
            }
        ],
        // 默认编译选项
        "latex-workshop.latex.recipe.default": "first",
        // 清空中间文件
        "latex-workshop.latex.clean.fileTypes": [
            "*.aux",
            "*.bbl",
            "*.blg",
            "*.idx",
            "*.ind",
            "*.lof",
            "*.lot",
            "*.out",
            "*.toc",
            "*.acn",
            "*.acr",
            "*.alg",
            "*.glg",
            "*.glo",
            "*.gls",
            "*.ist",
            "*.fls",
            "*.log",
            "*.fdb_latexmk",
            "*.bcf",
            "*.run.xml",
            // "*.synctex.gz"
        ]
    // ======================== LaTeX 设置 END ========================
}
```