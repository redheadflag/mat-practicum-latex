\clearpage -- Like \newpage, but also flushes all pending floats (figures, tables) before breaking
Recommended if you have figures/tables that might float

\newcommand{\mydate}{April 5, 2026} -- macro 

\expandafter ensures that \romannumeral 2 is evaluated first, producing ii, and then \uppercase converts it to II.

### \usepackage[a4paper, left=2.5cm, right=2.5cm]{geometry}
1. \usepackage{geometry}
Tells LaTeX to load the geometry package.
geometry is a package for setting page layout parameters: margins, paper size, text area, headers/footers, etc.
Without geometry, you’d have to manually set \textwidth, \oddsidemargin, \topmargin, etc., which is harder and error-prone.
2. [a4paper, left=2.5cm, right=2.5cm]
This is called the optional argument (inside square brackets) that configures the package when it’s loaded.


\usepackage{amsmath} -- for cases (systems of equations)

был ли \quad  в презентациях?
и вообще все теги проверить

добавить изображение. it should have a caption and be referenced to in the text.

include bibliography (at least two books or articles). Include also any internet
sources you are using. Cite at least one of them in the text
-
**\sloppy** relaxes LaTeX's line-breaking strictness, which eliminates underfull/overfull \hbox
warnings in bibliography entries — it's the standard approach when entries contain long URLs
or untreatable text like italic dashes.

поправить стиль всего документа с учетом всего что мы проходили на занятиях. вкинуть нейросети для обучения файлы.

разобраться с таблицами.

что такое \renewcommand 

\renewcommand redefines an existing command (as opposed to \newcommand which  
creates a new one).                                       
                                                                            
Syntax:                                                                       
\renewcommand{\commandname}{new definition}                                   
                                                        
In the file it's used in two places:
                                                                            
1. Footnote symbol — temporarily swaps the footnote marker to †, then restores
it:                                                                          
\renewcommand{\thefootnote}{\dag}   % change to †                             
\footnote{...}                                            
\renewcommand{\thefootnote}{\arabic{footnote}}  % restore to 1, 2, 3...       
                                                                        
2. Proof end symbol — replaces the default □ with ♠:                          
\renewcommand{\qedsymbol}{$\spadesuit$}                                       
                                                                            
If you tried to use \newcommand{\qedsymbol}{...} instead, LaTeX would throw an
error because \qedsymbol already exists. \renewcommand is specifically for   
overriding existing definitions. 


что значат команды со звездочками? какое правило?

