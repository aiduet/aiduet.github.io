# paper

A poster for one page. One plate, a title, a verse, a colophon.

`paper` is a single sheet: a portrait figure takes the top, one column of
text sits under it, and a hairline closes the page at the bottom. It is meant
to be the front of something — a home page with the navigation not yet added.
Everything on it is a token, so the next pass changes the words and the
figure without touching the frame.

## What is on it

- **The plate.** A 9:16 portrait frame. Today it holds a painted placeholder
  because there is no photograph yet; `background-image` on `.plate` is the
  one line to change when there is.
- **The stack.** Two columns: a title at 600 with the verse under it, and a
  spaced label opposite. The columns meet on one baseline.
- **The colophon.** A date, a credit, and one hairline that is the same rule
  as the plate's edge.

## Type

Jost, self-hosted, three subset files (latin, latin-ext, italic) — 55 KB
before compression. 600 carries the title and every label, 400 carries the
verse. Nothing depends on a third party at runtime.

Ume green is the only hue and it stays on words: the dot, the focus ring, the
selection. Surfaces are white and the plate's own colour.

## Files

```text
/
├── index.html
├── public/
│   ├── favicon.svg
│   └── fonts/
└── src/
    ├── tokens.css     # every colour, size, and distance on the page
    ├── fonts.css      # @font-face + unicode ranges
    └── poster.css     # the layout
```

## Running it

Any static server from the repo root:

```bash
python3 -m http.server 4400 --bind 0.0.0.0
```

No build step, no dependencies, no framework. Substitution values live in
`src/tokens.css`; the wording lives in `index.html`.
