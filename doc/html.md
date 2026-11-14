# html

Renders markdown blocks as HTML.

<a id="render-blocks"></a>

## `render-blocks`

```knave
(defn render-blocks (blocks))
(type render-blocks
  (fn ((ref (slice block))) string))
```

Renders each block and joins them with newlines.
