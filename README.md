

# <a name="Summary"></a>Summary
Some LaTex templates ready for use or to compare how certain things can be accomplished.


- [How to use - general](#How-to-general)
 - [The template files](#How-to-general)
 - [Basics](#Basics)
 - [Chapters, sections, etc.](#Chapters-general)
 - [Mathematics](#Mathematics)
 - [Additional packages](#Additional)
 - [Troubleshooting](#Trouble)
- [How to use - template specific](#How-to-specific)
 - [Thesis](#Thesis)
   - [Front matter, preface and table of contents](#Front)
   - [Chapters, sections, etc.](#Chapters-theis)
 - [Report](#Report)
 - [Letter](#Letter)


# <a name="How-to-general"></a>How to use - general



## <a name="Files"></a>The template files
All the template files have to be in the same directory for this template to work properly.



## <a name="Basics"></a>Basics
Basically, all you need to care about is the main file. As usual the content is put in between `\begin{document}` and `\end{document}`, while new packages can be included before `\begin{document}`, etc. .



## <a name="Chapters-general"></a> Chapters, sections, etc.
Chapters, sections, etc. work as usual with some addional commands depending on the template.


## <a name="Mathematics"></a>Mathematics
The general mathematics-packages are included (`amsmath`,`amsthm`,`amsfonts`,`amssymb`,`mathtools`).

The usual theorem/definition theorems are predefined and can be created by `\begin{X}... \end{X}` where `X` is

X | name
---|---
`deff` | Definition
`thm` | Theorem
`lemm` | Lemma
`cor`| Corollary
`prop`| Proposition
`prf`| Proof
`rem`| Remark
`exm`| Example

There are also `VarThm`, `VarLemm`, `VarCor` and `VarDef` that allow for custom names by using `\renewcommand{\VarThmName}{Your Name}` before `\begin{Var...}... \end{Var...}`, e.g.
```latex
\renewcommand{\VarThmName}{Definition and Lemma}
\begin{VarDef}
  Your Definition
\end{VarDef}
```

Furthermore, some highlight-boxes are predefined that can be accessed by `\begin{Y}... \end{Y}`, where `Y` is `framedef`, `framethm`, `framelemm`, `framecor`, `framerem`, `frameexm` or `frameproof`. Of course the highlight-boxes can be used freely and combined with any of the theorem environments.


## <a name="Additional"></a>Additional packages
For convenience, some other packages are included by default. If you want to use a specific package, you can include it in the main.tex file. It is recommended however, to check if the particular package is already included in the Thesis_Setup.tex file, as changing the oreder of the package inclusion could break some things.


## <a name="Trouble"></a>Troubleshooting
A general advice if unknown errors occur, is to delete the temporary files, e.g. .aux files etc. (not .bib and not .ist files).



# <a name="How-to-specific"></a>How to use - template specific

## <a name="Thesis"></a>Thesis




file | purpose
-----|--------
Thesis_Setup.tex| Configuration of the document and definition of the commands. Changes of the layout should be made here.
main.tex| The main file that loads the setup. Here you can put the content of the document. It is adviesd to write the contents in seperate files that can then be loaded by `\input{Your_File.tex}`.
title_page.tex | Thesis_Setup loads this file to produce the title page. So use this file to create your title page as usual.
index_style.ist| This file defines the style of the index. The package `imakeidx` is loaded by default.
Literature.bib| BibTex literature file that is loaded.

### <a name="Front"></a>Front matter, preface and table of contents
The front matter, i.e. title page, table of contents and intentional blank pages, to start the first chapter on a right page, can be created by `\FrontNoPreface`. If you want to include a preface, use `\FrontMatter{Preface title}{Content}` instead. The content can be any LaTex code as usual, e.g. new sections and subsections.

### <a name="Chapters-theis"></a>Chapters, sections, etc.
Chapters, sections, etc. work as usual. There are however two new commands. `\ChapterStart{text}` (right after `\chapter{title}`) creates a chapter description. `\PartWithText{part title}{part text}` allows to create a new part with text on the part page.


## <a name="Report"></a>Report

file | purpose
-----|--------
Report_Setup.tex| Configuration of the document and definition of the commands. Changes of the layout should be made here.
main.tex| The main file that loads the setup. Here you can put the content of the document. It is adviesd to write the contents in seperate files that can then be loaded by `\input{Your_File.tex}`.
index_style.ist| This file defines the style of the index. The package `imakeidx` is loaded by default.
Literature.bib| BibTex literature file that is loaded.

## <a name="Letter"></a>Letter
file | purpose
-----|--------
Letter.tex| Both content and format
