# footnote-relative-links-repro

Minimal reproduction: relative links inside footnotes are not rewritten
on the repository home page.

## Test

1. Body link: [docs/a.md](docs/a.md)
2. Footnote link: see footnote.[^rel]
3. Workaround, root-relative link in a footnote: see footnote.[^abs]

[^rel]: Relative: [docs/a.md](docs/a.md)
[^abs]: Root-relative: [docs/a.md](/blaumohn/footnote-relative-links-repro/blob/main/docs/a.md)

## Expected

All three links open `docs/a.md`.

## Actual (on the repository home page)

- Link 1 works: `href` is rewritten to `/blaumohn/footnote-relative-links-repro/blob/main/docs/a.md`.
- Link 2 returns 404: `href` stays `docs/a.md` and resolves to `github.com/blaumohn/docs/a.md`.
- Link 3 works.

The same README viewed at `/blob/main/README.md` does not show the bug,
because the unrewritten link happens to resolve correctly there.
