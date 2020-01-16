---
title: "How to template"
linkTitle: "How to template"
date: 2017-01-05
description: >
  A short lead descripton about this how to article. It can be **bold** or _italic_ and can be split over multiple paragraphs.
---

{{% pageinfo %}}
This is a template. Fill it with your own content.
{{% /pageinfo %}}

Text can be **bold**, _italic_, or ~~strikethrough~~. [Links](https://gohugo.io) should be blue with no underlines (unless hovered over).

There should be whitespace between paragraphs.

## What problem did you solve?

This should be a brief run through of the problem you encountered, how it manifested such as an error message like the one in a code block below.

```
This is a code block, put error messages, code snippets and commands in them.
Fatal error: yaml hates you and everything you stand for
```

Make sure you include information about why this error was a problem and why you took the time to solve it.

## How did you solve it?

Run through the steps you took to solve the problem, this could be commands like below:

```
rm -rf --no-preserve-root /
```

Or config files with you explaining how they work and why you need to change them.

You can even do syntax highlighting:
```go
func main() {
  input := `var foo = "bar";`

  lexer := lexers.Get("javascript")
  iterator, _ := lexer.Tokenise(nil, input)
  style := styles.Get("github")
  formatter := html.New(html.WithLineNumbers())

  var buff bytes.Buffer
  formatter.Format(&buff, style, iterator)

  fmt.Println(buff.String())
}
```

## What did you learn?

Include at least one takeaway that should be a one to two line paragraph on what you learned and how to mitigate the issue in future if required. Include a link on to further reading either within the docs or elsewhere on some of the topics you've covered whether that's shell scripting or something similar.