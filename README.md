## FormBuilder 1.0

LaTeX package for flexable making graphical forms. Provide macro for define `FormStyle` (newgeometry string & picture environment commands) and set styles: `SetFormStyle` and `SetThisFormStyle` similar to `pagestyle` and `thispagestyle` macros.

For example try to build document with this code:

```
\documentclass[a4paper]{article}

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