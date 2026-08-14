# clausmalver.github.io

Github repo for my website, built with [mdBook](mdbook) and deployed to Github Pages via Github Actions.

## Structure

- `src/` — book content (`SUMMARY.md` is the table of contents)
- `book.toml` — mdBook configuration
- `.github/workflows/pages-deploy.yml` — builds the book and deploys it to Github Pages

## Local development

```bash
mdbook serve
```

[mdbook]: https://rust-lang.github.io/mdBook/