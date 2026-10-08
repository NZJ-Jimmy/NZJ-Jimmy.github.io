# NZJ-Jimmy.github.io

Personal homepage and notes built with MkDocs Material.

## Structure

- `main`: MkDocs source
- `gh-pages`: generated static site
- `docs/linux`: Git submodule pointing to `E-Vertin/GNU-Linux-Guides`

## Local preview

```bash
git clone --recurse-submodules https://github.com/NZJ-Jimmy/NZJ-Jimmy.github.io.git
cd NZJ-Jimmy.github.io
python -m pip install mkdocs-material
mkdocs serve
```
