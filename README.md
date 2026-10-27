# James Wang's website

Personal academic website built with Jekyll and the [Academic Pages](https://github.com/academicpages/academicpages.github.io) theme.

## Editing the site

- `_pages/about.md`: home page, biography, and education.
- `_pages/publications.md`: publications and paper links.
- `_pages/teaching.md`: teaching and course-development experience.
- `_data/navigation.yml`: header navigation and the CV link.
- `_config.yml`: profile, contact information, and site settings.
- `_sass/_themes.scss`: font families and shared theme settings.
- `_sass/layout/_base.scss`: heading sizes and body line spacing.
- `_sass/layout/_page.scss`: education dates, sub-bullets, and paragraph spacing.
- `images/japan pfp.jpg`: current profile photo.

The template's demo pages and collections have been removed. The remaining pages are About, Publications, Teaching, and the 404 page; the CV links directly to its PDF. Jekyll still generates `sitemap.xml` for search engines.

## Running locally

Install Ruby and Bundler, then run:

```sh
bundle config set --local path 'vendor/bundle'
bundle install
bundle exec jekyll serve --host 127.0.0.1 --port 4000
```

Open <http://localhost:4000>. Content and stylesheet changes rebuild automatically; restart the server after changing `_config.yml`.

To check a production build:

```sh
JEKYLL_ENV=production bundle exec jekyll build
```

Docker (`docker compose up`) and the VS Code dev container configuration are also available.

## JavaScript and math support

The JavaScript bundle contains navigation, theme switching, and the shared UI helpers. After editing `assets/js/_main.js` or its plugins, rebuild the committed bundle:

```sh
npm install
npm run build:js
```

Add `math: true` to a page's front matter when it needs MathJax. Publications enables it; other pages avoid loading the math library.

## Updating the CV

The navigation's CV link opens `files/cv/James_Wang_CV_compiled.pdf` in a new browser tab. Its editable LaTeX source is stored beside it at `files/cv/James_Wang_CV_compiled.tex`.

Edit the source and compile it with a LaTeX installation:

```sh
pdflatex -output-directory=files/cv files/cv/James_Wang_CV_compiled.tex
```

Alternatively, replace both files with updated exports. Keep these filenames so the navigation link stays valid, and commit both the source and PDF together.

## Theme and license

Shared layouts, includes, styles, and JavaScript support the site, including navigation, dark mode, icons, and math in publications. These remain part of the theme infrastructure. Crimson Pro is loaded from Google Fonts.

Academic Pages is based on [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes). See [LICENSE](LICENSE) for the theme's license and attribution.
