# blocks

Groups markdown source into blocks.

<a id="block"></a>

## `block`

```knave
(defenum block)
```

A block of markdown: a heading, paragraph, code block, list or table.

<a id="block/bullet-list"></a>

## `block/bullet-list`

```knave
(defenum block)
```

No documentation.

<a id="block/code-block"></a>

## `block/code-block`

```knave
(defenum block)
```

No documentation.

<a id="block/heading"></a>

## `block/heading`

```knave
(defenum block)
```

No documentation.

<a id="block/numbered-list"></a>

## `block/numbered-list`

```knave
(defenum block)
```

No documentation.

<a id="block/paragraph"></a>

## `block/paragraph`

```knave
(defenum block)
```

No documentation.

<a id="block/table"></a>

## `block/table`

```knave
(defenum block)
```

No documentation.

<a id="parse-blocks"></a>

## `parse-blocks`

```knave
(defn parse-blocks (source))
(type parse-blocks
  (fn ((ref str)) (vec block)))
```

Groups source lines into blocks.
