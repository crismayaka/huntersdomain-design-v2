# Hunters Domain — design review

Live: https://crismayaka.github.io/huntersdomain-design-v2/

A published copy of the design set, for review in a real browser.

- `/` — the review index, with a V1 / V2 switch
- `/v1.html` — V1, frozen. A verbatim copy of `templates/design/v1-pages.html`
- `/v2/*.html` — the twelve V2 pages
- `blocks.css`, `tokens.css`, `fonts.css`, `fonts/` — the shared styles and self-hosted faces

## Do not edit these files here

Everything except `index.html` is generated from `templates/design/` in the private
`prod-outd-huntersdomain` repo, which is the source of truth. Publishing happens with one
command run from that repo:

```
pnpm design:sync
```

It copies the templates, fails if any internal link would escape the site, pushes here, then
fetches all twelve pages back and checks they are byte-identical. Hand edits to the pages,
styles or fonts are overwritten on the next run.

`index.html` is the exception: it is maintained here by hand.
