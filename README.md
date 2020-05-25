## Springer LNCS LaTeX Template

This is the fix of the bug of the [original][1] Springer LNCS LaTeX
Template (version 2.20 10-Mar-2018). When the original version is used
with [hyperref][2] package and `envcountsame` and `envcountsect`
options some references are broken. For example, if two lemmas are
defined in two different sections, the reference to the second lemma
brings to the definition of the first one:

    \documentclass[envcountsame,envcountsect,runningheads]{llncs}
    \usepackage{hyperref}
    
    \begin{document}
    
    \section{First Section}
    \begin{lemma}
       \label{lemma:first}
       First lemma in the first page of the first section.
    \end{lemma}
    \begin{theorem}
       Smart theorem.
    \end{theorem}
    \newpage
    \section{Second Section}
    \begin{lemma}
       \label{lemma:second}
       Second lemma on the second page.
    \end{lemma}
    Click \ref{lemma:second} and go to the first page.
    
    \end{document}

[1]: https://www.springer.com/gp/computer-science/lncs/conference-proceedings-guidelines?countryChanged=true
[2]: https://ctan.org/pkg/hyperref