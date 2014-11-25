## FormBuilder 1.0

LaTeX package for flexable making graphical forms. Provide macro for define `FormStyle` (newgeometry string & picture environment commands) and set styles: `SetFormStyle` and `SetThisFormStyle` similar to `pagestyle` and `thispagestyle` macros.

For example try to build document with this code:

```
\documentclass{article}

\usepackage{formbuilder}
\NewFormStyle{test}{top=5cm}{\put(30mm,30mm){NEW FORM STYLE!}}

\begin{document}
	
	A
	
	\newpage
	
	B
	\SetThisFormStyle{test}
	
	\newpage
	
	C
	
	\newpage
	
	D
	
	\newpage
	
	E
	
\end{document}
```

Package defaults:

```
\NewFormStyle{default}{noheadfoot,nomarginpar,top=2cm,bottom=2cm,inner=2cm,outer=2cm}{%
\linethickness{0.5mm}
\put(15mm,15mm)  {\line(1,0){180mm}}
\put(15mm,282mm) {\line(1,0){180mm}}
\put(15mm,15mm)  {\line(0,1){267mm}}
\put(195mm,15mm) {\line(0,1){267mm}}
\put(15mm,5mm)   {\slshape FORMBUILDER DEFAULT STYLE}}
\SetFormStyle{default}
```

Also package sets default pagestyle to `empty`.