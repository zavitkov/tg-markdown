# Markdown to Telegram MarkdownV2 Converter

## Description

[Telegram Bot API](https://core.telegram.org/bots/api) has several options to format [sending messages](https://core.telegram.org/bots/api#sendmessage) with a parameter _parse_mode_. One of them is [MarkdownV2](https://core.telegram.org/bots/api#markdownv2-style). 

It has similar syntax to normal markdown, however it can be a problem to convert already existent Markdown text to Telegram MarkdownV2.

## Usage

```go
package main 

import (
    "github.com/zavitkov/tg-markdown"
    "fmt"
)

func main() {
    markdown := `This is **bold** *italic* ~strikethrough~ text with [wrapped](https://github.com/zavitkov/tg-markdown) link and unwrapped link: https://github.com/zavitkov/tg-markdown`

    tgMarkdownV2 := tg_markdown.ConvertMarkdownToTelegramMarkdownV2(markdown)
    fmt.Println(tgMarkdownV2)
}
```