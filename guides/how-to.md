## Contents <!-- omit from toc -->
- [How to select fonts](#how-to-select-fonts)
- [How to format lists](#how-to-format-lists)
- [How to format title headers](#how-to-format-title-headers)
- [How to design the top banner](#how-to-design-the-top-banner)
- [How to adjust margins](#how-to-adjust-margins)
- [How to format page numbering](#how-to-format-page-numbering)
- [How to adjust spacing](#how-to-adjust-spacing)
- [How to add image, icon and color](#how-to-add-image-icon-and-color)


## How to select fonts

The default font in `LaTeX` is `Computer Modern`. If you want the recruter to know that you have used LaTeX without telling that you have used LaTeX then you should use this font. But, its sans-serif version isn't the prettiest, and it lacks small caps. There is a darker version of it called `mlmodern` which is a more modern adaptation with added features. 

There are two ways to change fonts in LaTeX. The first way is by using the fonts that come with LaTeX itself (when you compile with `pdfLaTeX`). But, if you have your own fonts and want to use those, you'll need to use either`XeLaTeX` or `LuaLaTeX`. You can use [The LaTeX Font Catalogue](https://tug.org/FontCatalogue/) for a comprehensive list of available fonts and their corresponding commands.

To change the default document font load its corresponding package in the preamble like `\usepackage{tgtermes}` for Times New Roman. To make sans-serif as your default font you have to mention it to LaTeX like so 
```latex
%% Helvetica
\usepackage{helvet}
\renewcommand{\familydefault}{\sfdefault}

%% or for Roboto
\usepackage[sfdefault]{roboto}
```

To change the font only for a certain part use the command `\fontfamily{font-code}\selectfont`.

To directly select a font-size and the corresponding baseline-skip setting use `\fontsize{font-size}{baseline-skip}\selectfont`. The baseline-skip value determines the distance between baselines of text in a paragraph, so you won't usually see its effect when used in only one line.


## How to format lists

We use the `enumitem` package to format lists. There are three basic list environments 
1. enumerate (numbered list), 
2. itemize (bulleted list) and 
3. description.

Formatting wise we want to decrease the line spacing between list items and align it with the margin. You can provide the formatting commands both locally or globally with a `<key>=<value>` syntax. To remove the vertical space altogether in all lists: `\setlist{nosep}` and to remove only the vertical spacing between list items use `noitemsep`. `itemsep=0pt` provides slightly more spacing. 

Typical setting for resume would be: `\setlist[itemize]{left= 0pt .. 1.5em, noitemsep}`

## How to format title headers

`titlesec` package is used to format `\section{}`,`\subsection{}` and `\subsubsection{}` headers. 

```latex
\titleformat{⟨command⟩}[⟨shape⟩]{⟨format⟩}{⟨label⟩}{⟨sep⟩}{⟨before-code⟩}[⟨after-code⟩]

\titlespacing{⟨command⟩}{⟨left⟩}{⟨before-sep⟩}{⟨after-sep⟩}[⟨right-sep⟩]
```

*Note*: `hyperref` package doesn't like when you put `\hfill` in the section title (since it messes up TOC). To avoid such warnings you can use `\usepackage[bookmarks=false]{hyperref}`.

## How to design the top banner

Centered Name in large size and contact details below it is the simple and efficient way to do it. 

```latex
\begin{center}
  {\huge\bfseries Rover Résumé} \par\medskip

  Address Line 1, City, State $|$ 
  email@example.com $|$ 
  phone: (123) 456 7890 
\end{center}
```

## How to adjust margins

You can use `fullpage` package to set all 4 mar­gins to be ei­ther 1 inch or(=) 1.5 cm. 

For more fine grained options use `geometry` package.

## How to format page numbering

`fancyhdr` package is used to format the footer which contains the page numbers.


```latex
\usepackage{fancyhdr}
\usepackage[page]{totalcount}
   
\renewcommand{\headrulewidth}{0pt}	
\fancyhf{}							
\cfoot{Rover Resume -- Page \thepage{} of \totalpages}
```


## How to adjust spacing

`\vspace{}`, `\hfill`.

## How to add image, icon and color

Use `fontawesome` or `fontawesome5` for icons.