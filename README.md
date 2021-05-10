# <a name="Summary"></a>Summary

* [How to use - general](#How-to-general)
  * [The template files](#How-to-general)
* [Basics](#Basics)
  * [Chapters, sections, etc.](#Chapters-general)
  * [Mathematics](#Mathematics)
  * [Additional packages](#Additional)
  * [Troubleshooting](#Trouble)
* [How to use - template specific](#How-to-specific)
  * [Thesis](#Thesis)
     * [Front matter, preface and table of contents](#Front)
     * [Chapters, sections, etc.](#Chapters-theis)
  * [Article](#Article)
  * [Letter](#Letter)
  * [Tikz graphics](#Tikz)


# <a name="How-to-general"></a>How to use - general



## <a name="Files"></a>The template files
All the template files have to be in the same directory for the respective template to work properly.



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


## <a name="Additional"></a>Additional packages and global commands
For convenience, some other packages are included by default. If you want to use a specific package, you can include it in the CustomPackages.tex file. It is recommended however, to check if the particular package is already included in the main.tex file, as changing the order of the package inclusion could break some things.

Furthermore, global command definitions can be put into the CustomPackages.tex. In some cases, definitions/settings that are made/set in main.tex can be redefined/changed here, to overwrite the definitions/settings from main.tex.


# <a name="How-to-specific"></a>How to use - template specific

## <a name="Thesis"></a>Thesis


file | purpose
-----|--------
main .tex| Configuration of the document and definition of the commands.
content.tex| Here you can put the content of the document. It is advised to write the contents in further separate files that can then be loaded by `\input{Your_File.tex}`.
title_page.tex | The template loads this file to produce the title page. So use this file to create your title page as usual.
index_style.ist| This file defines the style of the index. The package `imakeidx` is loaded by default.
Literature.bib| BibTex literature file that is loaded.

### <a name="Front"></a>Front matter, preface and table of contents
The front matter, i.e. title page, table of contents and intentional blank pages, can be created by `\FrontNoPreface`. If you want to include a preface, use `\FrontMatter{Preface title}{Content}` instead. The content can be any LaTeX code as usual, e.g. new chapters, sections and subsections.

### <a name="Chapters-theis"></a>Chapters, sections, etc.
Chapters, sections, etc. work as usual. There are however two new commands. `\ChapterStart{text}` (right after `\chapter{title}`) creates a chapter description. `\PartWithText{part title}{part text}` allows to create a new part with text on the part page.


## <a name="Article"></a>Article

file | purpose
-----|--------
main.tex| Same as Thesis template.
conten.tex| Same as Thesis template.
index_style.ist| Same as Thesis template.
Literature.bib| Same as Thesis template.

## <a name="Letter"></a>Letter
Template for standard letters.

## <a name="Tikz"></a>Tikz Graphics
Template for standalone Tikz graphics.
