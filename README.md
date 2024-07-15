# Markdown to Telegram MarkdownV2 Converter

## Description

[Telegram Bot API](https://core.telegram.org/bots/api) has several options to format [sending messages](https://core.telegram.org/bots/api#sendmessage) with a parameter _parse_mode_. One of them is [MarkdownV2](https://core.telegram.org/bots/api#markdownv2-style). 

It has similar syntax to normal markdown, however it can be a problem to convert already existent Markdown text to Telegram MarkdownV2.

## Features

1. Convert Markdown Bold (`**Bold**`) to Telegram MarkdownV2 Bold (`*Bold*`)
2. Convert Markdown Italic (`*Italic*` or `_Italic_`) to Telegram MarkdownV2 Italic (`_Italic_`)
3. Convert Markdown Strikethrough (`~Strikethrough~`) to Telegram MarkdownV2 Italic (`~Strikethrough~`)
4. Parse unwrapped links (`https://example.com`) and wrap them (`[https://example.com](https://example.com)`)
5. Parse Markdown inline code and code blocks and escape special chars inside them for Telegram MarkdownV2.

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
	
    //output: This is *bold* _italic_ ~strikethrough~ text with [wrapped](https://github.com/zavitkov/tg-markdown) link and unwrapped link: [https://github\.com/zavitkov/tg\-markdown](https://github.com/zavitkov/tg-markdown)
}
```