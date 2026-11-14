# strings

String helpers over shared and owned text.

<a id="after"></a>

## `after`

```knave
(defn after (text start))
(type after
  (fn ((ref str) usize) (ref str)))
```

Returns the part of `text` from `start`.

<a id="before-first"></a>

## `before-first`

```knave
(defn before-first (text separator))
(type before-first
  (fn ((ref str) (ref str)) (ref str)))
```

Returns the part of `text` before the first `separator`.

<a id="contains?"></a>

## `contains?`

```knave
(def contains?)
(type contains?
  (fn ((ref str) (ref str)) bool))
```

True when `text` contains `part`.

<a id="ends-with?"></a>

## `ends-with?`

```knave
(def ends-with?)
(type ends-with?
  (fn ((ref str) (ref str)) bool))
```

True when `text` ends with `suffix`.

<a id="escape-html"></a>

## `escape-html`

```knave
(defn escape-html (text))
(type escape-html
  (fn ((ref str)) string))
```

Escapes `&`, `<`, `>` and quotes for HTML.

<a id="find-any-from"></a>

## `find-any-from`

```knave
(def find-any-from)
(type find-any-from
  (fn ((ref str) (ref str) usize)
    (option usize)))
```

Returns the first position at or after `start` that holds a mark.

<a id="find-from"></a>

## `find-from`

```knave
(def find-from)
(type find-from
  (fn ((ref str) (ref str) usize)
    (option usize)))
```

Returns the first position of `part` at or after `start`.

<a id="first-char?"></a>

## `first-char?`

```knave
(defn first-char? (text test))
(type first-char?
  (fn ((ref str) (fn (char) bool)) bool))
```

True when the first character of `text` passes `test`.

<a id="join"></a>

## `join`

```knave
(def join)
(type join
  (fn ((ref (slice string)) (ref str))
    string))
```

Joins `parts` with `separator`.

<a id="leading-count"></a>

## `leading-count`

```knave
(defn leading-count (text mark))
(type leading-count
  (fn ((ref str) char) usize))
```

Counts the leading `mark` characters in `text`.

<a id="owned"></a>

## `owned`

```knave
(defn owned (text))
(type owned (fn ((ref str)) string))
```

Copies `text` into an owned string.

<a id="replace-all"></a>

## `replace-all`

```knave
(def replace-all)
(type replace-all
  (fn ((ref str) (ref str) (ref str))
    string))
```

Replaces every `part` in `text` with `replacement`.

<a id="starts-with?"></a>

## `starts-with?`

```knave
(def starts-with?)
(type starts-with?
  (fn ((ref str) (ref str)) bool))
```

True when `text` starts with `prefix`.
