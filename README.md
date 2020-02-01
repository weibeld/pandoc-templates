# Pandoc templates

Some custom [pandoc templates](https://pandoc.org/MANUAL.html#templates).

See also the [official pandoc templates](https://github.com/jgm/pandoc-templates) and the [user-contributed pandoc templates](https://github.com/jgm/pandoc/wiki/User-contributed-templates).

## Usage

To convert the Markdown file `file.md` via LaTeX to PDF with the [`weibeld.latex`](weibeld.latex) template, you can do as follows:

```bash
pandoc \
  -o file.pdf \
  --template https://raw.githubusercontent.com/weibeld/pandoc-templates/master/weibeld.latex  \
  file.md
```

To use a different [syntax highlighting](https://pandoc.org/MANUAL.html#syntax-highlighting) style, you can do:

```bash
pandoc \
  -o file.pdf \
  --highlight-style=tango \
  --template https://raw.githubusercontent.com/weibeld/pandoc-templates/master/weibeld.latex  \
  file.md
```

To set custom values for the template variables, you can use the [`-V`](https://pandoc.org/MANUAL.html#general-writer-options) option:

```bash
pandoc \
  -o file.pdf \
  -V toc -V toc-depth=2 -V parindent=16pt -V parskip=0pt \
  --template https://raw.githubusercontent.com/weibeld/pandoc-templates/master/weibeld.latex  \
  file.md
```

## Markdown files

You can use any ordinary Markdown file as the input file:

```markdown
# Title

Hello world

## Subtitle

Foo bar
```

You may also add a Markdown front matter with the title, author, date, etc. of the document (this will be rendered in the output PDF):

```markdown
---
title: My Document
author: Joe Doe
date: 1 January 2020
---

# Title

Hello world

## Subtitle

Foo bar
```

Last but not least, you can set values for all the template variables in the front matter:

```markdown
---
title: My Document
author: Joe Doe
date: 1 January 2020
toc: true
toc-depth: 2
parindent: 16pt
parskip: 0pt
---

# Title

Hello world

## Subtitle

Foo bar
```
