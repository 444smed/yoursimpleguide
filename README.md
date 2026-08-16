# yoursimpleguide.com

Quarto site hosted on GitHub Pages.

## Files

- `index.qmd` — site home, list of sections
- `homeschool/index.qmd` — homeschool overview and shared links
- `homeschool/brailee.qmd` — Brailee's assignment and links
- `homeschool/addy.qmd` — Addy's assignment and links
- `styles.scss` — colors and spacing
- `_quarto.yml` — menu and settings

## Posting a new assignment

Open the girl's file. Replace what is inside the block that starts with
`::: {.assignment}` and ends with `:::`. Leave those two lines alone.

To keep the old one, move it under "Past assignments" like this:

    ::: {.callout-note collapse="true"}
    ## August 13
    Old assignment text here.
    :::

## Adding a link

Inside a `::: {.linklist}` block, add a line:

    - [Course name](https://the-real-url.com)

## Publishing changes

1. Save the file.
2. In a terminal, `cd` to this folder, run `quarto render`.
3. In GitHub Desktop: write a summary, Commit to main, then Push origin.

Live about a minute later.

## Do not delete

`CNAME` and `.nojekyll`. They keep the custom domain and the styling working.

## Adding a new section later

1. Make a folder, for example `house/`, with an `index.qmd` inside it.
2. Add it to the `navbar` list in `_quarto.yml`.
3. Add a line for it under "Sections" on `index.qmd`.

## Changing the accent color

Top of `styles.scss`, the line `$blue: #1a3fb8;`. Replace the hex code.
