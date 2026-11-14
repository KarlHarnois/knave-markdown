# lib

Renders a subset of markdown to HTML.

<a id="render-markdown"></a>

## `render-markdown`

```knave
(defn render-markdown (source))
(type render-markdown
  (fn ((ref str)) string))
```

Renders a subset of markdown to HTML.

```knave
(render-markdown "# Install")
```

Headings get an `id` and an anchor link, and `knave` code blocks are
highlighted.
