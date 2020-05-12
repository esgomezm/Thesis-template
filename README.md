PhD thesis template
========================
> A LuaLaTeX PhD thesis template for Universidad Carlos III de Madrid. Bioengineering Department.

[![License MIT](http://img.shields.io/badge/license-MIT-brightgreen.svg)](license.md)
[![Version](http://img.shields.io/badge/version-2.2-brightgreen.svg)](https://github.com/BIIG-UC3M/Thesis-template)

## Author(s)
*   Asier Marcos Vidal <asmarcos@ing.uc3m.es>
*   Later minor changes: Pedro M. Gordaliza <pmacias@ing.uc3m.es>

--------------------------------------------------------------------------------
## Features

*   [x] Conforms to the Student Registry PhD dissertation guidelines and PhD guidelines

*   [x] Supports LuaLaTeX, Available in Overleaf

*   [x] Adaptive Title Page: Title page adapts to title length

*   [] Title page with both College and University crests.

*   [] Print / On-line version: Different layout and hyper-referencing styles 

*   [x] Pre-defined and custom fonts (Times / Fourier / Latin Modern / ancient greek) with math support

*   [x] Supports system fonts (LuaLaTeX)

*   [] Pre-defined and custom bibliography style support (authoryear / numbered / custom)

*   [] Custom page styles: 3 Different Header / Footer styles

*   [x] Pre-defined and custom margin size

*   [x] A separate abstract with thesis title and author name, along with the titlepage can be generated by passing the argument `abstract` to the document class.

*   [x] Option to generate only specific chapters and references without the frontmatter and title page. Useful for review and corrections.

*   [] Draft mode: Draft water mark, timestamp, version numbering and line numbering

*   [] Add supervisor and/or advisor to your PhD thesis 


--------------------------------------------------------------------------------

## Building your thesis - XeLaTeX

### Using latexmk (Unix/Linux/Windows)

This template supports `XeLaTeX` compilation chain. To generate  PDF run

    latexmk -xelatex thesis.tex
    makeindex thesis.nlo -s nomencl.ist -o thesis.nls
    latexmk -xelatex -g thesis.tex

## Building your thesis - LuaLaTeX

### Using latexmk (Unix/Linux/Windows)

This template supports `XeLaTeX` compilation chain. To generate  PDF run

    latexmk -pdflatex=lualatex -pdf thesis.tex


## Building your thesis - LaTeX / PDFLaTeX

### Using latexmk (Unix/Linux/Windows)

This template supports `latexmk`. To generate DVI, PS and PDF run

    latexmk -dvi -ps -pdf thesis.tex



### Using the make file (Unix/Linux)

The template supports PDF, DVI and PS formats. All three formats can be generated
with the provided `Makefile`.

To build the `PDF` version of your thesis, run:

    make


This build procedure uses `pdflatex` and will produce `thesis.pdf`.

To produce `DVI` and `PS` versions of your document, you should run:


    make BUILD_STRATEGY=latex

This will use the `latex` command to build the document and will produce
`thesis.dvi`, `thesis.ps` and `thesis.pdf` documents. You will need psutils installed

Clean unwanted files

To clean unwanted clutter (all LaTeX auto-generated files), run:

    make clean

__Note__: the `Makefile` itself is take from and maintained at
[here](http://code.google.com/p/latex-makefile/).

### Shell script for PDFLaTeX (Unix/Linux)

Usage: `sh ./compile-thesis.sh [OPTIONS] [filename]`

[option]  compile: Compiles the PhD Thesis

[option]  clean: removes temporary files - no filename required

### Using the batch file on Windows OS (PDFLaTeX)

*    Open command prompt and navigate to the directory with the tex file. Run:

    `compile-thesis-windows.bat`.

*    Alternatively, double click on `compile-thesis-windows.bat`


-------------------------------------------------------------------------------

## Usage details

 * [] Thesis information such as title, author, year, degree, etc., and other meta-data can be modified in `thesis-info.tex`

### Title page


### Abstract separate


* [] To generate the separate abstract and the title page, make sure the following commands are in the preamble section of `thesis.tex` file:

        \ifdefineAbstract
        \includeonly{Abstract/abstract}
        \fi

### Chapter mode

*  The chapter mode allows user to only print specific chapters along with references. By default, it excludes everything else in the front matter and appendices. This can done by using `chapter` option in the document class in `thesis.tex`. Ignore subsequent warnings about skipping sections (if any).

*  To generate the separate abstract and the title page, make sure the following commands are in the preamble section of `thesis.tex` file:

		\ifdefineChapter
			\includeonly{Chapter3/chapter3}
		\fi

### Draft

`draft` adds a watermark `draft` text with timestamp and version number at the top or
the bottom of the page. Pagewise line numbering is added on every page. `draft` settings can be tweaked in the `preamble.tex`.

* Use `draftclassic` in the document class options to use the default book class draft mode.

* To add figures in draft mode (default enabled), in the preamble set `\setkeys{Gin}{draft=false}`. `draft=true` disables figures

* To change the watermark text
      \SetDraftText{DRAFT}

* To change the position of the watermark text. Default watermark position is top. The location can be changed to (top / bottom)
      \SetDraftWMPosition{bottom}

* To change the draft version. Default draft version is v1.0.
      \SetDraftVersion{v1.1}

* Watermark grayscale value can be modified. Text grayscale value (should be between 0-black and 1-white). Default value is 0.75
      \SetDraftGrayScale{0.8}


## To-do Notes
* 


## General guidelines

*   Remember LuaLatex!!
*   In order to generate the thesis at different qualities. The template contains folders for figures storage at different formats. Just change the root path under `\graphicspath` at main_phd.tex
-------------------------------------------------------------------------------

## Frequently Asked Questions

#### _Q1_: Where can I find the thesis formatting guidelines this class is based on?



#### _Q2_: Where can I find newer versions of the University of Cambridge crest/logos?



#### _Q3_: Where can I find the guidelines to submit my thesis and requirements?


#### _Q4_: How can I count the number of words in my thesis?

Overleaf: 
 `Menu --> Word Count`

You can run the following command (Linux/Unix):
    `ps2ascii thesis.pdf | wc -w` (eg., result 2713 words)

or
    `pdftotext thesis.pdf | wc thesis.txt -w` (eg., result 2690 words)

or
    `texcount -inc *.tex` (eg., result 2341 words)


#### _Q5_: I found a bug in the template. Where do I report bugs?

You can report issues at
[our GitHub repository](https://github.com/BIIG-UC3M/Thesis-template).



--------------------------------------------------------------------------------
## Troubleshooting warnings
------------------------------------------------------------------------

## Known issue(s) / Bugs / Feature requests



--------------------------------------------------------------------------------

## Acknowlegments