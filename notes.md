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



What the presentations say about tables (slides 45–58)
                                                                                                                                                
  Key rules from 3-typesettingtext-16.pdf:
                                                                                                                                                
  - Use tabular for the actual grid; table (floating environment) wraps it with caption                                                         
  - Placement: h (here), t (top), b (bottom), p (float-only page), ! (override restrictions). Default: [tbp]
  - \caption{...} adds the "Table N:" prefix automatically                                                                                      
  - \label must come after \caption — because it references the caption number                                                                  
  - Use \ref to reference the float in text                                                                                                     
  - \listoftables prints a list of tables                                                                                                       
                                                                                                                                                
  Our file correctly has \caption before \label inside the table environment.                                                                   
                                                                                                                                              
  ---                                                                                                                                           
  Other style issues I notice                                                                                                                 
                                                                                                                                                
  One thing the presentation highlights (slide 40–41): the abstract environment should be used for article-class documents instead of
  \section*{Abstract}. Our file uses the section approach. This changes the visual appearance slightly (the abstract environment formats it     
  differently), so I won't change it without your confirmation — but it is what the slides teach. 



  When hyperref builds the PDF, it creates a bookmarks panel (the clickable outline on the left in PDF viewers). Bookmark text must be plain    
  text — no math, no $...$.                                                                                                                   
                                                                                                                                                
  Your section heading \section{Lines in \rthree} is used for two things:                                                                       
                                                                                                                                                
  1. The visible heading in the document — math works fine here                                                                                 
  2. The PDF bookmark string — math is not allowed here                                                                                       
                                                                                                                                                
  \texorpdfstring{A}{B} lets you give two versions:                                                                                           
  - A — used in the document (your math: $\R^3$)                                                                                                
  - B — used in the PDF bookmark (plain text: R^3)                                                                                              
   
  So:                                                                                                                                           
  \section{Lines in \texorpdfstring{\rthree}{R^3}}                                                                                            
  means: "show Lines in R³ in the document, but write Lines in R^3 in the PDF bookmarks".                                                       
                                                                                                                                              
  Without it, hyperref tries to use $\R^3$ as a bookmark string, fails, strips the math tokens, and emits those warnings.                       
                                                                                                                                                
❯ what is hyperref?                                                                                                                             
                                                                                                                                                
● hyperref is a LaTeX package that adds interactive features to your PDF:                                                                       
                                                                                                                                              
  - Clickable links — \ref, \cite, \url become blue/colored clickable links                                                                     
  - PDF bookmarks — the outline panel in PDF viewers (table of contents you can click)                                                          
  - PDF metadata — title, author stored in the file properties                                                                                  
                                                                                                                                                
  Without hyperref, a LaTeX PDF is just static paper. With it, clicking Table~\ref{tab:distances} in the PDF jumps you to that table.           
                                                                                                                                                
  You already have it in your file:                                                                                                             
  \usepackage[colorlinks,linkcolor=red,citecolor=green,urlcolor=blue,...]{hyperref}                                                           
  That's why your cross-references are colored and clickable.