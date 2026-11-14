# line-syntax

Recognizes the syntax of one markdown line.

<a id="anchor-id"></a>

## `anchor-id`

```knave
(defn anchor-id (line))
(type anchor-id (fn ((ref str)) string))
```

Returns the id in an HTML anchor line.

<a id="anchor-line?"></a>

## `anchor-line?`

```knave
(defn anchor-line? (line))
(type anchor-line?
  (fn ((ref str)) bool))
```

True when the line is an HTML anchor.

<a id="blank?"></a>

## `blank?`

```knave
(defn blank? (line))
(type blank? (fn ((ref str)) bool))
```

True when the line holds only whitespace.

<a id="bullet-item?"></a>

## `bullet-item?`

```knave
(defn bullet-item? (line))
(type bullet-item?
  (fn ((ref str)) bool))
```

True when the line starts a bullet item.

<a id="bullet-text"></a>

## `bullet-text`

```knave
(defn bullet-text (line))
(type bullet-text
  (fn ((ref str)) string))
```

Returns the text after the bullet marker.

<a id="fence-language"></a>

## `fence-language`

```knave
(defn fence-language (line))
(type fence-language
  (fn ((ref str)) string))
```

Returns the language tag after a code fence marker.

<a id="fence?"></a>

## `fence?`

```knave
(defn fence? (line))
(type fence? (fn ((ref str)) bool))
```

True when the line holds a code fence marker.

<a id="heading-level"></a>

## `heading-level`

```knave
(defn heading-level (line))
(type heading-level
  (fn ((ref str)) usize))
```

Returns the number of leading `#` characters.

<a id="heading-text"></a>

## `heading-text`

```knave
(defn heading-text (line))
(type heading-text
  (fn ((ref str)) string))
```

Returns the text after the heading hashes.

<a id="heading?"></a>

## `heading?`

```knave
(defn heading? (line))
(type heading? (fn ((ref str)) bool))
```

True when the line is a heading of level one to six.

<a id="numbered-item?"></a>

## `numbered-item?`

```knave
(defn numbered-item? (line))
(type numbered-item?
  (fn ((ref str)) bool))
```

True when the line starts a numbered item.

<a id="numbered-text"></a>

## `numbered-text`

```knave
(defn numbered-text (line))
(type numbered-text
  (fn ((ref str)) string))
```

Returns the text after the numbered marker.

<a id="table-cells"></a>

## `table-cells`

```knave
(defn table-cells (row))
(type table-cells
  (fn ((ref str)) (vec string)))
```

Splits a table row into trimmed cells.

<a id="table-row?"></a>

## `table-row?`

```knave
(defn table-row? (line))
(type table-row? (fn ((ref str)) bool))
```

True when the line starts with a pipe.
