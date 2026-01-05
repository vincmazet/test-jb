# Introduction


+++ {"part": "abstract"}
This is my abstract!
+++






Bonne année et bonne santé !

$$
a = b + c
$$



Lorsque je fais des changements :
1. j'enregistre et voit en direct via le serveur local (jupyter-book start)
2. je clique sur les +, écrit un commit et Ctrl+Entrée pour pusher sur le site



(https://jupyterbook.org/stable/get-started/export-pdfs/)

I am a book about ... something! Wikipedia has [information about books](wiki:book): hover over the link for more information.

* **jupyter-book init** : initialise a project.
* **jupyter book init --write-toc** : autogenerate a Table of Contents
* **jupyter-book start** : built-in server that renders your book as a locally-served website.
* **jupyter book build --pdf** : building a pdf

## Export PDFs

**jupyter book templates list --pdf**

- 🟢 lapreprint-typst
- arxiv_nips : An arXiv compatible template based on the NIPS 2018 Style
- arxiv_two_column : A two column arXiv compatible template
- frontiers : A template for the Frontiers In range of Journals
- volcanica : A template for submissions to the Volcanica journal
- curvenote : A paper styled template using the custom environments and styling to match Curvenote Web
- plain_latex : A minimal template that only uses vanilla LaTeX commands and environments
- plain_latex_book : A plain latex book theme
- springer : Official template for Springer journals
- ⚠️ ieee-typst : IEEE Template from Typst app, updated as a MyST template
- ⚠️ plain_typst_book : Easily create beautiful books in Typst

**jupyter book templates list --typst lapreprint-typst**

LaPreprint Typst Template : lapreprint-typst
Parts:
- abstract (required) - An abstract is a short summary of your research paper or report. A good abstract will prepare readers for the detailed information to follow, communicate the essence of the article and help readers take away and remember key points.
- summary - Plain language summary
- acknowledgements - Acknowledgements printed in the margin
- availability - Data availability statement printed in the margin

Options:
- logo (file) - An image path that is shown in the top right of the page
- kind (string) - The "kind" of the content, e.g. "Original Research" - shown as the title of the margin content on the first page
 -short_citation (string) - The short citation used in the document header. By default, it is automatically determined from the author names.
- heading_numbering (string) - Heading numbering style.

Finalement :
* **jupyter book build intro.md --tex** et faire pour chaque fichier. Mais impose de nettoyer le tex et d'avoir une classe pour le template avant de compiler en pdf "à la main".
* **jupyter book build --pdf** compile tous les fichiers en pdf avec le format défini dans le frontmatter de myst.yml :
```
  exports:
    - format: pdf
      template: lapreprint-typst
      articles:
        - intro.md
        - page2.md
        - page3.md
```

## Publish web

https://jupyterbook.org/stable/get-started/publish/