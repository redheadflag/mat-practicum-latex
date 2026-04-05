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