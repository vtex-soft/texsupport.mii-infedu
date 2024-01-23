# texsupport.vu-infedu

LaTeX author support files for the journal  
[Informatics in Eduaction](https://infedu.vu.lt/journal/INFEDU)


## Contents

The following files are given in the repository (or directly in `.zip` archive):

- `infedu_sample.tex` - a sample article
- `infedu_sample.pdf` - a sample article
- `infedu_template.tex` - a template file
- `infedu.cls` - journal class file
- `infedu.bst` - Bibtex style
- `biblio.bib` - Bibtex DB sample

## Setup

-   Clone the repository or download the `.zip` archive.
-   Install LaTeX style files (`infedu.cls`, `infedu.bst`) 
    in your TeX system or place them in the same directory where your `*.tex` file is.
-   Read the instructions (`infedumanual.pdf`) for the preparation of your LaTeX document.
-   Use the template file `infedu_template.tex` to prepare your manuscript.

### LaTeX document preamble content

The preamble of your LaTeX document should look like this:

```
\documentclass{infedu}
\volume{0}
\issue{0}
\pubyear{2022}
\articletype{research-article}
\doi{0000}

\begin{document}
\begin{frontmatter}
\pretitle{Research Article}
\title{A sample document}

\author[a]{\inits{F.}\fnms{Firstname1} \snm{Surname1}\thanksref{c1}\ead[label=e1]{aut1@foo.com}\bio{bio1}}
\author[b]{\inits{S.}\fnms{Firstname2} \snm{Surname2}\thanksref{f1}\ead[label=e2]{aut2@foo.com}\bio{bio2}}
\thankstext[type=corresp,id=c1]{Corresponding author.}
\thankstext[id=f1]{Simple footnote.}
\address[a]{Address of the First author, \institution{University}, \cny{Country name}}
\address[b]{Address of the Second author, \institution{University}, \cny{Country name}}

\dedicated{Dedicated to}

\begin{abstract}
...
\end{abstract}

\begin{keywords}
\kwd{Sample}
\kwd{\LaTeX}
\end{keywords}

\end{frontmatter}

    Your publication content

\end{document}
```

### Comments

* `\author` command has optional parameter that serves as and identifier, and which can be used in
`\address` field to identify address belonging. Macros `\inits`, `\fnms`, `\snm` stands for author’s initials,
first names and surname accordingly. Use `\thanksref` and `\thankstext` macro to identify
and print title page footnotes. In adition `type=corresp` key in `\thankstext` will use `*` as a
footnote mark. It is used for correspondig author identification. Email address should be provided in a
`\ead{label=id}` macro.
* Labels **c1**, **f1** are used for thanks;
* thanks text `type=corresp` marks corresponding author;
* Labels **e1**, **e2** are used to print electronic addresses.
`hyperref` package is loaded in the class so they will be made into hyperlinks;
* Please add different keywords in `\kwd` macro;
* Headings are generated automatically by printing authors (in even page) and title (in odd page). Use
`\runtitle{}` and `\runauthor{}` if necessary to change auto-generated ones.

### Bibliography
Use bibtex database and `infedu.bst` style for bibliography items.
```
\bibliographystyle{infedu}
\bibliography{biblio}% your bibliography database
```
To procude bbl file issue `bibtex` in a command promt.
You will get higly customised bbl file.

### Biography
Authors involved in this research can be described in biography environments. Put the authors name
into `\author` macro. Biographies should be typsed at the end of article right after bibliography.
```
\begin{biography}
\author{F. Surname1} obtained his PhD in ...
\end{biography}
```
## Compiling
Please use latex or pdflatex to compile a manuscript.
```
pdflatex paper
bibtex paper
pdflatex paper
pdflatex paper
```

## Submition
Please submit a single zip file which contains the following files:
* paper.tex
* paper.pdf or paper.ps
* paper.bbl
* *.eps,*.pdf (EPS or PDF images)
* <your-file>.bib bibtex data base

## Bug reports

Please submit bug reports and/or feature requests
at [GitHub page](https://github.com/vtex-soft/texsupport.mii-infedu/issues) or 
[latex-support@vtex.lt](mailto:latex-support@vtex.lt).

