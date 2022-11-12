# Usage

## Copy templates to user folder

Copy this directory `latex` and it's contents to your user template folder, e.g. `~/.local/share/jupyter/nbconvert/templates/`.

To find out the correct template path in `data`, call the following command:

```bash
$ jupyter --paths

config:
    /home/bk/.jupyter
    /home/bk/jupyter-env/etc/jupyter
    /usr/local/etc/jupyter
    /etc/jupyter
data:
    /home/bk/.local/share/jupyter
    /home/bk/jupyter-env/share/jupyter
    /usr/local/share/jupyter
    /usr/share/jupyter
runtime:
    /home/bk/.local/share/jupyter/runtime
```

## Call `nbconvert` command

Call `nbconvert` command to produce LaTeX or PDF output either:

```bash
$ jupyter nbconvert jupyter_notebook.ipynb --to latex
```

Or:

```bash
$ jupyter nbconvert jupyter_notebook.ipynb --to pdf
```

## Including figures

The handling of figures was inspired by and adapted from http://blog.juliusschulz.de/blog/ultimate-ipython-notebook#figures.

## Citing and literature references

Install packages `texlive-bibtex-extra` and `biber` for using BibLaTeX first.

Insert citations in markdown cells as e.g.:

```html
<cite data-cite="Kasper_Studie_I4.0_2019">(Kasper, 2019)</cite>
```

Provide the BibLaTeX formatted library with the notebooks `latex_metadata`, e.g.:

```json
"latex_metadata": {
        "affiliation": "Elsewhere Inc.",
        "author": "You",
        "bib": "literature/notebook.bib",
        "cover_image": "images/Cover_image.pdf",
        "email": "you@email.org",
        "title": "Your title of your paper"
    },
```

Call the custom build script:

```bash
$ ./build_latex.sh compile your_notebook.ipynb
```

Cleanup temporary build artefacts:

```bash
$ ./build_latex.sh clean your_notebook.ipynb
```








