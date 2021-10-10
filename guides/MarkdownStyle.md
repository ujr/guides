
# Markdown Style Guide

This document is a style guide for writing Markdown.

1. [Background](#background)
2. [Guidelines](#guidelines)
3. [Markdownlint](#markdownlint)
4. [EditorConfig](#editorconfig)
5. [References](#references)


## Background

Markdown is plain text that follows a few conventions
such that it is possible to render formatted output,
while the input is still readable as plain text, without
obtrusive markup (hence *markdown*).

Markdown was proposed in 2004 by John Gruber and Aaron Swartz.
It is described at <https://daringfireball.net/projects/markdown/>.
Extensions exist, for example “GitHub Flavored Markdown”.
CommonMark is a standardization attempt.

Sometimes, Markdown provides more than one way to achieve
a desired formatting. This guide makes choices in these cases.
The choices attempt to balance *readability* and *maintainability*
of the plain text. They are certainly subjective.


## Guidelines

- Use `.md` as the file extension. Example: `README.md`
- Avoid long lines. Stick to the project's line limit.
  URLs and tables are exceptions.
- Avoid trailing whitespace except two blanks for hard
  line breaks (alternatively, a backslash `\` before
  the newline may be used, but it is not as portable).

### Text Formatting

- Prefer `**bold**` and `*italic*` over `__bold__` and `_italic_`
  (reason: the latter works less reliably when used within words).
- Many renderers offer `~~strikethrough~~` for ~~strikethrough~~.
- Underlining is not generally offered; stay away.

You may have to escape an underscore or an asterisk
if they occur literally in your text: `foo\_bar`.
Use `***triple***` to get ***triple*** (bold and italic).
Note that `**` translates to `<strong>` (not `<b>`)
and `*` translates to `<em>` (not `<i>`).

### Headings

- Use a blank line before and after a heading.
- May use two blank lines before a heading.
- Do not skip heading levels.
- Avoid deep nesting of headings.
- Prefer ATX-style `#` and `##` for H1 and H2
  over underlining (`===` and `---`)
- Put a blank between the hash(es) and the heading text
  (`#Title` not `#Title`)

Underlining headings may look better in plain text,
but `#` and `##` are easier to maintain and most
editors nicely highlight headings anyway.

### Lists

- Use lazy numbering for long lists.
- Use explicit numbering for short lists.
- Prefer `-` over `*` and `+` for unordered lists.
- Place number or bullet in the first column.
- Use a blank line before and after a list.

To avoid starting a (nested) list if your text starts
with an ordinal number, escape the period like `12. Blah`.

For nested lists, place the number or bullet
in the same column as the outer text starts.
(This may not be the typographically best solution,
but it is easy to maintain consistently.)

```text
Easier to maintain:        Looks better in text:

- First outer item           * First outer item
- Second outer item          * Second outer item
  - nested                       * nested
  - item                         * item
- Last outer item            * Last outer item

Opt for easy maintainability.
```

### Code

- Use triple quotes for longer code blocks.
- Declare the language, if possible.
- Use four-space indenting for short snippets,
  especially if many in sequence.
- Inline code goes between single backticks: `int foo;`

Backticks may be used to escape Markdown metacharacters
(instead of the backslash; beware that you get the code font).

### Miscellaneous

- Link to headings like this: `[link text](#document-layout)`
  assuming there is a heading “Document Layout”. This is
  not part of the original Markdown and may not be supported.
- Avoid HTML in Markdown documents.
  Likely exceptions are `<sub>` and `<sup>`.
- Complex or large tables are very hard to maintain.
  Consider lists instead.
- Horizontal rules: prefer `---` over `***` and `___`.
- Put URLs and mail addresses in angle brackets to turn
  them into links: `<me@host.org>`

### Document layout

```markdown
# Title

Intro or overview.

ToC (optional)

## Section

Content.

## See also

- <https://link.to.info>

May call this “References” instead.
```


## Markdownlint

[Markdownlint](https://github.com/DavidAnson/markdownlint)
is a “linter” (static analysis) tool for Node.js with
configurable rules. Integrations for VS Code and other
editors/tools exist.

Rules are configured in a `.markdownlint.json` file
typically in the root of the project directory.

A `.markdownlint.json` file that starts with the full ruleset
(`default: true`) but relaxes a few for compatibility with the
guidelines above might look like this:

```json
{
    "default": true,
    "code-block-style": false,
    "no-multiple-blanks": false,
    "heading-style": { "style": "atx" },
    "line-length": { "tables": false },
    "no-inline-html": { "allowed_elements": ["sub", "sup"]}
}
```


## EditorConfig

An `.editorconfig` excerpt suitable for Markdown files:

```ini
[*.md]
indent_style = space
trim_trailing_whitespace = false
insert_final_newline = true
charset = utf-8
```


## See also

- Gruber's original at <https://daringfireball.net/projects/markdown/>
- The Markdown Guide at <https://www.markdownguide.org>
- EditorConfig at <https://editorconfig.org>
- Markdownlint at <https://github.com/DavidAnson/markdownlint>
- CommonMark at <https://commonmark.org/>
- Google's [Markdown style guide](http://google.github.io/styleguide/docguide/style.html)
- [GitHub Flavored Markdown](https://github.github.com/gfm/)
