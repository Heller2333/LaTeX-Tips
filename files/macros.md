# 宏
```latex
\def \indicator {\mathbbm{1}}

% 条件期望
\newcommand\given[1][]{\:#1\vert\:}
\newcommand\givenn[1][]{\:#1\middle\vert\:}

% 范数
\let\oldnorm\norm
\let\norm\ndefined
\newcommand\norm[1]{\left\| #1 \right\|}

\newcommand\inner[2]{\langle #1, #2 \rangle} % 内积
\newcommand\abs[1]{\left| #1 \right|}
\newcommand\ceil[1]{\lceil #1 \rceil}
\newcommand\sbr[1]{\left( #1 \right)} % 小括号 
\newcommand\mbr[1]{\left[ #1 \right]} % 中括号
\newcommand\bbr[1]{\left\{ #1 \right\}}

\newcommand\term[1]{\textsc{term}\,(\textsc{#1})}

\def \D {\mathcal{D}}
\def \E {\mathbb{E}}
\def \H {\mathcal{H}}
\def \I {\mathcal{I}}
\def \K {\mathcal{K}}
\def \O {\mathcal{O}}
\def \Ot {\tilde{\O}}
\def \R {\mathbb{R}}
\def \Rcal {\mathcal{R}}
\def \S {\mathcal{S}}
\def \T {\mathrm{T}}
\def \W {\mathcal{W}}
\def \X {\mathcal{X}}
\def \Y {\mathcal{Y}}

\def \g {\mathbf{g}}
\def \u {\mathbf{u}}
\def \v {\mathbf{v}}
\def \w {\mathbf{w}}
\def \x {\mathbf{x}}
\def \y {\mathbf{y}}
\def \z {\mathbf{z}}

\DeclareMathOperator*{\poly}{poly}
\DeclareMathOperator*{\argmax}{arg\,max}
\DeclareMathOperator*{\argmin}{arg\,min}

\newcommand{\Authornote}[2]{{\small\textcolor{DSgray}{\sf$<<<${  #1: #2
}$>>>$}}}
\newcommand{\xxnote}[1]{{\Authornote{XX-XX}{#1}}}

% 定义公式环境
\let\proof\relax
\let\endproof\relax
\usepackage{amsthm}
\let\proof\relax
\let\endproof\relax
\def \endenv {\hfill\raisebox{1pt}{$\P$}\smallskip}
\newenvironment{proof}{\par\noindent{\bf Proof\ }}{\hfill\BlackBox\\[2mm]}
\renewcommand\qedsymbol{$\blacksquare$}

% 以下环境中的字体是斜体
\newtheorem{myThm}{Theorem}
\newtheorem{myFact}{Fact}
\newtheorem{myClaim}{Claim}
\newtheorem{myLemma}{Lemma}
\newtheorem{myObservation}{Observation}
\newtheorem{myProp}{Proposition}
\newtheorem{myProperty}{Property}
\newtheorem{myCor}{Corollary}

% 以下环境中的字体是正体
\theoremstyle{definition}
\newtheorem{myAssum}{Assumption}
\newtheorem{myConj}{Conjecture}
\newtheorem{myDef}{Definition}
\newtheorem{myExample}{Example}
\newtheorem{myNote}{Note}
\newtheorem{myProblem}{Problem}
\newtheorem{myRemark}{Remark}
\newtheorem*{myProofSketch}{Proof Sketch}
\newtheorem*{myAnalysis}{\underline{Analysis}} 
```



## 解释
1. ```\xxnote```命令：