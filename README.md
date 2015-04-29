## FormBuilder 1.0

LaTeX package for flexable making graphical forms. Provide macro for define `FormStyle{<setup code>}{<drawings>}` (that define setup code and background draw hook in picture environment with 0,0 at bottom left corner of sheet) and provide set-style command: `ApplyFormStyle`. Apply of new style execute `\clearpage`, then execute setup style code and change draw background hook.

For example try to build document with this code:

```
%%% example.tex
\documentclass{extarticle}
\usepackage{formbuilder}

\NewFormStyle{mystyle}
	{ %
		\newgeometry{noheadfoot,nomarginpar,top=5cm,bottom=5cm,inner=2cm,outer=2cm}}
	{ %
		\linethickness{1.5mm} %
		\put(15mm,40mm)  {\line(1,0){180mm}} %
		\put(20mm,35mm){\textbf{My form style}}} %

\begin{document}

    A
    \vfill
    A

    \newpage
    B
    \vfill
    B
    
    \newpage
    C
    \vfill
    C

    \ApplyFormStyle{mystyle}
    D
    \vfill
    D

    \newpage
    E
    \vfill
    E

\end{document}
```

Package defaults:

```
\NewFormStyle{formbuilder}
	{%
		\newgeometry{noheadfoot,nomarginpar,top=2cm,bottom=2cm,inner=2cm,outer=2cm}}
	{%
		\linethickness{0.5mm}
		\put(15mm,15mm)  {\line(1,0){180mm}}
		\put(15mm,282mm) {\line(1,0){180mm}}
		\put(15mm,15mm)  {\line(0,1){267mm}}
		\put(195mm,15mm) {\line(0,1){267mm}}
		\put(15mm,10mm){\slshape FORMBUILDER DEFAULT STYLE}}

\ApplyFormStyle{formbuilder}
```

Also package sets default pagestyle to `empty`.