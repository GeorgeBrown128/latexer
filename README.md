# latexer
Script to compile a LaTeX file each time it is updated.

I work on a remote filesystem which is often a bit slow, and it seems as 
though most tools don't like working on it. My PDF viewer in particular gets 
very upset, and pdflatex slows down quite a bit too. My solution was to 
re-purpose my [pander](https://github.com/GeorgeBrown128/pander) script to 
create a local workspace.

Sets up pdflatex and minted to work from the local temp directory. To use 
minted, use the following command in your LaTeX source:

```latex
\usepackage[__OUTPUTDIR__]{minted}
```

`__OUTPUTDIR__` is automatically replaced by the working directory. Be aware 
the `-shell-escape` flag is enabled by default. If you're not using minted, 
then remove this flag in the script for security.
