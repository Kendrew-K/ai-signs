# ai-signs

A Claude Code skill that checks writing and design for the things that make them read as AI-generated, and fixes them.

It runs before Claude writes or edits any content (emails, docs, website copy, headings) and checks for:

- **Words:** "delve", "tapestry", "seamless", "leverage" and more, each rated by severity
- **Sentence patterns:** "It's not X, it's Y", em dashes as connectors, a colon before the reveal, throat-clearing openers, closing lines that try to sound profound
- **Typography:** Inter for every role, no font pairing, Title Case on every heading
- **Color:** `#6366f1` indigo buttons, purple-to-blue gradients, pure gray neutrals
- **Layout:** hero, three equal cards, pricing, FAQ, with `rounded-2xl shadow-lg` on everything
- **Images:** extra fingers, plastic skin, shadows that point different ways

It also runs two tests. **Portability:** if a sentence could go on another company's page unchanged, it's filler. **Show, don't tell:** cut any line that calls something important instead of showing why.

## Install

```bash
git clone https://github.com/Kendrew-K/ai-signs.git
cp -r ai-signs/skills/ai-signs ~/.claude/skills/
```

On Windows, copy `skills\ai-signs` into `%USERPROFILE%\.claude\skills\`.

Restart Claude Code. The skill loads on its own whenever Claude is about to write content. You can also call it directly with `/ai-signs`, or ask it to "de-AI" a file.

## Credits

The sentence-level patterns are adapted from [petergyang/no-ai-slop](https://github.com/petergyang/no-ai-slop). Several UI and color checks come from a Fountain Institute article on AI design tells.

## License

MIT. Use it, fork it, change it.
