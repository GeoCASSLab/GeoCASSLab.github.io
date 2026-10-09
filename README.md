# GeoCASS Lab Website

Source for the website of the GeoCASS Lab at The University of Texas at Dallas: <https://geocasslab.github.io>

The lab is directed by [Dr. Alexander Michels](https://alexandermichels.github.io/) in the School of Economic, Political and Policy Sciences. We use geospatial
data science and cyberGIS to tackle societal challenges.

## Editing content

| To change...                | Edit                                                                  |
| --------------------------- | --------------------------------------------------------------------- |
| Home page text, lab address | `_pages/about.md`                                                     |
| People page                 | `_pages/profiles.md` (one block per person) plus a bio file per block |
| Member photos               | add to `assets/img/people/`, reference as `people/<file>`             |
| News items                  | `_news/` (one Markdown file per item)                                 |
| Projects                    | `_projects/`                                                          |
| Publications                | `_bibliography/papers.bib`                                            |
| Coauthor links              | `_data/coauthors.yml` (key = lowercase last name)                     |
| Email, GitHub, ORCID links  | `_data/socials.yml`                                                   |
| Site title, nav, settings   | `_config.yml`                                                         |

## Running locally

With Docker:

```bash
docker compose up -d
```

The site is served at <http://localhost:8080/>. Edits to content are picked up automatically, and edits to `_config.yml` restart the server. Stop it with
`docker compose down`.

Without Docker (Ruby and ImageMagick required):

```bash
bundle install
bundle exec jekyll serve
```

The site is then at <http://localhost:4000/>.

## Deployment

Pushes to `main` trigger `.github/workflows/deploy.yml`, which builds the site and publishes it to the `gh-pages` branch served by GitHub Pages.

## Acknowledgments

Built with [Jekyll](https://jekyllrb.com/) and the [al-folio](https://github.com/alshedivat/al-folio) starter by Maruan Al-Shedivat and contributors, used under the
MIT License (see [LICENSE](LICENSE)).
