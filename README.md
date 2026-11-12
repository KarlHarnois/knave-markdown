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

A subset, not CommonMark:

- Headings, optionally preceded by an `<a id="..."></a>` line that sets their anchor
- Paragraphs and fenced code blocks
- `- ` bullet lists and `1. ` numbered lists
- Pipe tables with a `| --- |` delimiter row
- Inline code, `*emphasis*`, `**strong**`, links and backslash escapes

## HTML output

- Headings get an `id` and an `<a class="anchor">` link to themselves.
- Code blocks render as `<pre><code class="language-<tag>">`, with one `<span class="line">` per line.
- `knave` code blocks get highlight spans such as `keyword`, `string` and `comment`.

## Develop

Run `direnv allow` once to load the [Nix](https://nixos.org/download/) dev shell, then use these commands:

```sh
knave test
knave fmt
knave task check-file-lengths
```
