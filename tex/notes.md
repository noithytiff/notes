# Notes for Tex

1. Useful macros.
Math
```tex
\DeclareMathOperator*{\argmin}{arg\,min}
\DeclareMathOperator*{\argmax}{arg\,max}
```

Editing color.
```tex
\newcommand\yaoedit[1]{{\color{red} #1}}
```

Abbreviation.
```tex
\newcommand{\eg}{{\em e.g.,\ }}
\newcommand{\ie}{{\em i.e.\ }}
\newcommand{\etc}{{\em etc.}}
\newcommand{\etal}{{\it et al.\ }}
```

Paragraph space.
```tex
\newcommand{\para}[1]{{\vspace{1pt} \bf \noindent #1 \hspace{6pt}}}
```

Packed item and enumerate.
```tex
\newenvironment{packed_itemize}{
	\begin{list}{\labelitemi}{\leftmargin=2em}
		\setlength{\itemsep}{1pt}
		\setlength{\parskip}{0pt}
		\setlength{\parsep}{0pt}
		\setlength{\headsep}{0pt}
		\setlength{\topskip}{0pt}
		\setlength{\topmargin}{0pt}
		\setlength{\topsep}{0pt}
		\setlength{\partopsep}{0pt}  
	}{\end{list}}

\newenvironment{packed_enumerate}{
	\begin{enumerate}
		\setlength{\itemsep}{3pt}
		\setlength{\parskip}{0pt}
		\setlength{\parsep}{0pt}
		\setlength{\headsep}{0pt}
		\setlength{\topskip}{0pt}
		\setlength{\topmargin}{0pt}
		\setlength{\topsep}{0pt}
		\setlength{\partopsep}{0pt}
	}{\end{enumerate}}
```

2. Two figures in a row.
```tex
\begin{figure*}[t]
    \begin{minipage}{.49\textwidth}
        \centering
        \includegraphics[width=\linewidth]{xxxx}
        \caption{xxxx}
        \label{fig:xxx}
    \end{minipage}
    \hfill
    \begin{minipage}{.49\textwidth}
        \centering
        \includegraphics[width=\linewidth]{xxxx}
        \caption{xxxx}
        \label{fig:xxxx}
    \end{minipage}
\end{figure*}
```

3. Two tables in a row.
```tex
\begin{table*}[!t]
    \centering
    \subtable[xxxxx.]{
        \begin{tabular}{@{}cccccc@{}}
        xxxxx
        \end{tabular}
        \label{tab:xxxxx}
    }
    \\
    \subtable[xxxxx.]{
        \centering
         \begin{tabular}{@{}cccccc@{}}
          xxxxxxx
        \end{tabular}
        \label{xxxxx}
    }
    \caption{xxxxxx.}
    \label{table:xxxxx}
\end{table*}
```

4. Resize table.
```tex
\resizebox{0.8\columnwidth}{!}{
    \begin{tabular}{|c|c|c|}
    xxxxxx
    \end{tabular}
 }
```

5. mbox.
```tex
\begin{figure}[t]
\centering
\mbox{
    \subfigure[CAPTION_TEXT_1]{
        \includegraphics[width=0.235\textwidth]{FIG_PATH_1}
        \label{fig:TAG_1}
    }
    \hfill
    \subfigure[CAPTION_TEXT_2]{
        \includegraphics[width=0.235\textwidth]{FIG_PATH_2}
        \label{fig:TAG_2}
    }
}
\caption{CAPTION_TEXT_3}
\end{figure}
```


6. Downsample eps figure.
```bash
eps2eps oldfile newfile
```

7. Remove embarrassing commands before uploading to arXiv.
```bash
perl -pe 's/(^|[^\\])%.*/\1%/' oldfilename newfilename
```
