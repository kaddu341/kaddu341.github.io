# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Awwab Azam's personal academic e-portfolio, built for the University Scholars Program at UF.
It is a static Jekyll site served by GitHub Pages as a user site at https://kaddu341.github.io.

Most content is factual biography: publications, talks, grades, GPA, test scores. Never invent,
embellish, or "round up" any of it. If a change needs a fact that isn't already in the repo, ask.

`assets/Awwab_Azam_CV.pdf` is the source of truth for the CV, research and coursework pages; read it
with `pdftotext -layout` when syncing them. Per-course grades come from a transcript the user keeps
outside this repo, so ask rather than guessing. That transcript also carries identifiers such as UFID
and date of birth, which must never reach the site.

One standing content rule covers the user's Princeton work. The site cites the talks given there,
by venue and title, and lists the skills and tools picked up there, such as the DFT software, under
Skills. It does not name the advisor, and it does not describe that research itself: no position
entry, no project description, no topic summary. Keep it to talks and skills.

Do not add new sections to the CV page uninvited. An experience section in particular is unwanted,
because listing one group implies the user works only with that group.

## Commands

```bash
bundle install                        # first-time setup; the bundle is installed and building cleanly
bundle exec jekyll serve --livereload # dev server at http://localhost:4000
bundle exec jekyll build              # write _site/
bundle exec jekyll build --unpublished # also render posts marked published: false
bundle exec jekyll doctor             # config/URL sanity check
```

There is no test suite, linter, or CI. Verification means: the build finishes without a Liquid or
kramdown error, and the affected page renders correctly in `jekyll serve`.

## Deployment

No workflow file exists, so GitHub Pages runs its own built-in Jekyll build on every push to `main`.
Consequences:

- The `github-pages` gem pins **Jekyll 3.10.0**, not 4.x. Jekyll 4 syntax and features will not work.
- Only plugins on GitHub Pages' allowlist run. Adding an arbitrary gem to `_config.yml` builds fine
  locally and then silently does nothing in production. `jekyll-feed` is the only plugin in use.
- `_site/` and `Gemfile.lock` are gitignored. The `_site/` directory present locally is stale build
  output; never edit it and never commit it.

## Structure and theme

Every page is a `.markdown` file at the repo root with front matter carrying its own `permalink`
(`research.markdown` to `/research/`, and so on). `index.markdown` uses `layout: home`; the others
use `layout: page`. Posts live in `_posts/`, and the single post there is `published: false`.

There are no `_layouts/`, `_includes/`, or `_sass/` directories. All HTML and CSS comes from the
**minima 2.5** theme gem. To change any markup or style, copy the file out of the gem
(`bundle show minima`) into a matching path in this repo, which overrides the gem's copy.

Two consequences of relying on stock minima:

- **Header nav order is alphabetical by file path**, currently Coursework, About, Research,
  Curriculum Vitae. Fix the order by adding a `header_pages` list to `_config.yml`.
- **`math: true` in `research.markdown` does nothing.** Stock minima has no MathJax or KaTeX
  include, and the built page contains neither. Rendering LaTeX requires adding a script tag via a
  layout or head override first.

Images and PDFs go in `assets/`, referenced by absolute site path such as `/assets/images/foo.png`.
`baseurl` is empty, so absolute paths are safe.
