# highlight

Highlights Knave code in fenced code blocks.

<a id="highlight-code"></a>

## `highlight-code`

```knave
(defn highlight-code (language code))
(type highlight-code
  (fn ((ref str) (ref str)) string))
```

Highlights `knave` code and escapes any other language.
