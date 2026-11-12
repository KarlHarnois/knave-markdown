# knave-markdown

[![CI](https://github.com/KarlHarnois/knave-markdown/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/KarlHarnois/knave-markdown/actions/workflows/ci.yml)
[![Knave v0.14.21](https://img.shields.io/badge/knave-v0.14.21-blue.svg)](https://github.com/knave-lang/knave/releases/tag/v0.14.21)
[![Nix flake](https://img.shields.io/badge/nix-flake-5277C3.svg?logo=nixos&logoColor=white)](flake.nix)

A [Knave](https://github.com/knave-lang/knave) library that renders a subset of markdown to HTML.

## Use

Add the library to your `project.knv`:

```lisp
(defproject my-site
  (libraries
    (knave-markdown :git "https://github.com/KarlHarnois/knave-markdown"
                    :rev "<commit>")))
```

Call `render-markdown` with the markdown text:

```lisp
(use knave-markdown render-markdown)

(render-markdown "# Install\n\nRun `knave test`.\n")
```

The call returns this HTML:

```html
<h1 id="install" aria-labelledby="install-title"><a class="anchor" href="#install" aria-label="Link to this section">#</a><span id="install-title">Install</span></h1>
<p>Run <code>knave test</code>.</p>
```

## Supported markdown

The library renders this subset of markdown, not full CommonMark:

- Headings from `#` to `######`. An `<a id="..."></a>` line before a heading sets the heading's anchor.
- Paragraphs.
- Fenced code blocks.
- Bullet lists with `- ` and numbered lists with `1. `.
- Pipe tables. The second line of a table is its delimiter row, such as `| --- |`, and does not render. Write `\|` for a pipe inside a cell.
- Inline code, `*emphasis*`, `**strong**`, `[links](target)` and backslash escapes.

## HTML output

- A heading gets an `id`, an `<a class="anchor">` link to itself, and its text in a `<span id="<id>-title">`. The `id` is the explicit anchor, or a slug of the heading text.
- A code block renders as `<pre><code class="language-<tag>">`, with each line in a `<span class="line">`.
- A code block tagged `knave` gets Knave highlighting. Each highlighted token sits in a `<span>` whose class names its kind:
  - `paren`
  - `definer`
  - `special`
  - `keyword`
  - `string`
  - `number`
  - `comment`
  - `result-arrow`
- A code block with any other tag renders as escaped text.
- A table renders as a plain `<table>` with a `<thead>` and a `<tbody>`.

## Develop

Run `direnv allow` once to load the [Nix](https://nixos.org/download/) dev shell, then use these commands:

```sh
knave test
knave fmt
knave task check-file-lengths
```
