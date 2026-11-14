# inlines

Renders inline markdown to HTML.

<a id="render-inlines"></a>

## `render-inlines`

```knave
(defn render-inlines (text))
(type render-inlines
  (fn ((ref str)) string))
```

Renders code spans, emphasis, strong text, links and escapes.
