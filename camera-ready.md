---
layout: page
title: Camera-Ready
description: Instructions for preparing a camera ready paper for publication on this website.
permalink: /camera-ready
---

GenAICHI papers are generally published here on this website under a CC BY 4.0 license; however, if you don't want to publish your workshop submission you don't have to. In general, we ask that authors send us one of the following options (through a form in CMT):

1. A clean PDF (see instructions below or [this example](https://www.overleaf.com/read/rxpnyjpgkfxm#ebf97a)) that they are happy to have hosted on our website under a [Creative Commons Attribution CC BY 4.0 License](https://creativecommons.org/licenses/by/4.0/) (authors retain copyright).
2. A working URL to a self-hosted version of their submission in either PDF or HTML. The link should be to something like arXiv, your own website, or an institutional repository but not a dropbox or onedrive link those disappear after a while.
3. No paper, but an updated abstract for our website, you take responsibility for distributing your paper under whatever way you might want to.

## Creating a clean GenAICHI PDF

GenAICHI uses the 1-column ACM Primary Article Template in `manuscript` mode as our proceedings template. 
We have a LaTeX code example below that puts the ACM template into 1-column `manuscript` mode, adds a footer with the workshop title to each page, and adds a CC BY 4.0 license note the first page.
You may adjust this template as you wish , but we expect a neat-and-tidy 1-column formatted PDF file for publication on our website.
This code is also available as an [example on Overleaf](https://www.overleaf.com/read/rxpnyjpgkfxm#ebf97a).


{% raw %}
```
%% Special GenAICHI Settings and Setup for ACM article template:
\documentclass[manuscript,screen,nonacm]{acmart} % the settings here are important!
\setcopyright{cc} %% CC BY 4.0 license
\acmConference[]{} %% this used to suppress the adresses footer, but not anymore apparently.


\newcommand{\workshopname}{GenAICHI: CHI 2025 Workshop on Generative AI and HCI}
%%
\newcommand\extrafootertext[1]{% this command adds a non-numbered footnote
    \bgroup
    \renewcommand\thefootnote{\fnsymbol{footnote}}%
    \renewcommand\thempfootnote{\fnsymbol{mpfootnote}}%
    \footnotetext[0]{#1}%
    \egroup
}

\AtBeginDocument{ % setup headers and footers
    \fancypagestyle{firstpagestyle}{
        \fancyhf{}
        \fancyfoot[L]{\sffamily\footnotesize \workshopname}%
        \fancyfoot[C]{\sffamily\footnotesize \thepage}
    }
    \fancyhf{}
    \fancyhead[L]{\sffamily\footnotesize\shorttitle}
    \fancyhead[R]{\sffamily\footnotesize\shortauthors}
    \fancyfoot[L]{\sffamily\footnotesize\workshopname}%
    \fancyfoot[C]{\sffamily\footnotesize\thepage}
}
%% End GenAICHI settings and setup

\begin{document}
% the rest of your document goes here
\end{document}
```
{% endraw %}

If you want to create your PDF with Word or another non-latex word processor, you can use the 1-column ACM template and add an equivalent footer if you wish. Our paper template looks like this:

![Example GenAICHI workshop paper]({% link images/genaichi-example-paper.jpg %})
