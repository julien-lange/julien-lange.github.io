# julien-lange.github.io

Single-page personal site, built by Jekyll on GitHub Pages. Pushing to `master`
deploys it.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole page: markup, prose, and the Liquid loops that render the data files. |
| `_data/publications.yml` | **The publication list.** Edit this to add papers. |
| `_data/links.yml` | The "Elsewhere" links. |
| `_config.yml` | Name, position, department, institution. |
| `assets/css/style.css` | All the styling, light and dark themes. |
| `images/profile.jpg` | The photo (square, 900×900). |

## Adding a publication

Open `_data/publications.yml` and add a block at the top (entries render in
file order, newest first):

```yaml
- title: The Title of the Paper
  authors: Some Coauthor, Julien Lange, Another Coauthor
  venue: POPL 2027
  year: 2027
  links:
    - name: DOI
      url: https://doi.org/...
    - name: arXiv
      url: https://arxiv.org/abs/...
```

`links` is optional, and can hold any number of entries (DOI, arXiv, code,
slides, …). `authors` is rendered verbatim. Papers are grouped under year
headings, so keep `year` consistent with `venue`.

That is the only file needed to touch for a new paper. Commit and push.

## Previewing locally

```sh
bundle install          # once
bundle exec jekyll serve # then open http://localhost:4000
```

`_config.yml` is only read at startup — restart the server after editing it.
