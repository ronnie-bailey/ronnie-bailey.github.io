---
title: Your Note Title Goes Here
date: 2026-07-05
tags: identity, zero-trust, add-your-own-tags
banner: posts/assets/your-image.jpg
summary: One or two sentences shown on the front page card. If you leave this out, the first paragraph of the note is used automatically.
---

Start writing here. Everything between the two `---` lines above is the "front matter" — the settings for this note. Everything below it is the note itself, written in plain Markdown.

## Quick reference

**Banner options.** The `banner:` line accepts an image (`.jpg`, `.png`), an animated gif (`.gif`), or a video (`.mp4`, `.webm`). Videos autoplay muted and loop — good for conference clips. Upload the file to the `posts/assets/` folder first, then reference it like the example above. You can also paste a full `https://` URL. Delete the `banner:` line entirely if a note doesn't need one.

**Tags.** Comma-separated, lowercase. Reuse the same tags across notes — that's what makes the tag cloud meaningful. Five or six recurring tags beat twenty one-offs.

**Formatting.** `## Heading` for sections, `**bold**`, `*italic*`, `> quote` for blockquotes, and images anywhere in the body with:

![A caption for the image](posts/assets/another-image.jpg)

**This file never appears on the site** because its name starts with an underscore. To publish a real note, copy this file's contents into a new file named like `2026-07-15-short-slug.md` in the `posts` folder.
