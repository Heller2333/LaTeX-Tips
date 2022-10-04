# git使用

## 教程

[史上最浅显易懂的git教程](https://www.liaoxuefeng.com/wiki/896043488029600)

这个教程覆盖了所有我们用得上的方法，强烈安利！

## 建议的目录结构

├── assets

│   ├── figure1.pdf

│   └── figure2.svg

├── .gitignore

└── main.tex

## 建议的gitignore文件

```gitignore
*.fls
*.aux
*.blg
*.log
*.bbl
*.fdb_latexmk
*.synctex.gz
*.pdf
!assets/*
```

- *.pdf 防止生成的pdf文件被git捕获

- !assets/* 确保asset中的figure等pdf能正常同步