---
title: "Markdown"
weight: 30
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---
{{< toc >}}

## Headings

```markdown
# H1
## H2
### H3
#### H4
```

Use one `#` per heading level. Leave a blank line before and after headings for better compatibility.

## Text formatting

| Result | Markdown |
|--------|----------|
| Bold | `**bold**` |
| Italic | `*italic*` |
| Bold and italic | `***bold and italic***` |
| Strikethrough | `~~strikethrough~~` |
| Inline code | `` `inline code` `` |

## Paragraphs and line breaks

Separate paragraphs with a blank line.

```markdown
First paragraph.

Second paragraph.
```

For a hard line break, end the line with two spaces or use `<br>`.

```markdown
First line  
Second line
```

## Lists

Unordered lists:

```markdown
- First item
- Second item
- Third item
```

Ordered lists:

```markdown
1. First item
2. Second item
3. Third item
```

Nested lists:

```markdown
- Parent item
  - Child item
  - Child item
- Parent item
```

Task lists:

```markdown
- [x] Done
- [ ] Not done
```

## Links

```markdown
[Link text](https://example.com)
[Link with title](https://example.com "Optional title")
<https://example.com>
```

Reference-style links keep long URLs out of the paragraph.

```markdown
Read the [docs][docs-link].

[docs-link]: https://example.com/docs
```

## Images

```markdown
![Alt text](image.png)
![Alt text](image.png "Optional title")
```

Alt text should describe the image for screen readers and for cases where the image cannot load.

## Blockquotes

```markdown
> A quoted paragraph.
>
> A second quoted paragraph.
```

Nested blockquotes:

```markdown
> Outer quote
>
> > Nested quote
```

## Code blocks

Use fenced code blocks with a language name for syntax highlighting.

````markdown
```bash
echo "hello"
```

```json
{
  "name": "example"
}
```
````

Indenting by four spaces also creates a code block, but fenced blocks are clearer.

## Tables

```markdown
| Name | Description |
|------|-------------|
| foo  | First item  |
| bar  | Second item |
```

Alignment:

```markdown
| Left | Center | Right |
|:-----|:------:|------:|
| A    | B      | C     |
```

## Horizontal rules

```markdown
---
```

Use horizontal rules sparingly to separate major sections.

## Escaping characters

Use a backslash when you need Markdown syntax to appear as literal text.

```markdown
\*not italic\*
\# not a heading
\[not a link\]
```

## HTML

Most Markdown renderers allow inline HTML.

```markdown
This is <mark>highlighted</mark>.
```

Use HTML only when Markdown cannot express the structure cleanly. Support varies by renderer.

## Footnotes

Footnotes are common in GitHub Flavored Markdown and many static site generators.

```markdown
Here is a claim with a note.[^1]

[^1]: This is the footnote text.
```

## Definition lists

Some renderers support definition lists.

```markdown
Term
: Definition text
```

Check your renderer before relying on this syntax.

## Common gotchas

- Put blank lines around headings, lists, blockquotes, and code blocks.
- Use fenced code blocks instead of indentation for multi-line code.
- Keep table rows simple; tables are fragile with long text or nested formatting.
- Prefer descriptive link text over raw URLs in prose.
- Check renderer-specific features before using footnotes, task lists, or definition lists.
