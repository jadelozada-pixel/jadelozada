---
name: add-clip
description: Add one or more of Jade's published stories to the Clips section of the site, using the headline, outlet and date exactly as published, then push so it goes live. Use when Jade runs /add-clip with one or more story links, or asks to add a clip or story to the site.
---

# Add a clip

Jade gives one or more links to stories she wrote. For each link, add the story to the Clips section of `index.html`, then push to main so the site updates.

## 1. Start from the latest version

Run `git pull --ff-only origin main` before changing anything.

## 2. Open each link and copy the details exactly

Open the link (WebFetch, or the web-fetch agent if WebFetch isn't available). From the published page, copy:

- **Headline:** the story's headline exactly as published, character for character, including capitalization, punctuation, quote marks and apostrophes. Take it from the headline on the page itself, not the browser tab title or a social-media title, which often add the outlet name or are shortened. Never rewrite, shorten, fix or tidy it.
- **Outlet:** the publication's name as it presents itself on the page (for example "The Washington Sun").
- **Date:** the date the story was first published, written the way the page shows it. If the page shows both a published and an updated date, use the published one.

**If anything is missing or uncertain, ask; don't guess.** If a link won't open, sits behind a paywall or login, or you can't find the headline, outlet or publish date with confidence, don't add that story. Add the ones you could confirm, then ask Jade for the headline, outlet and date of the others, and add them exactly as she gives them.

Skip a link that's already in the Clips list and say so.

## 3. Add it to the Clips section

The Clips section is `<section id="clips">` in `index.html`. Stories go in a `<ul class="clips">` list, newest first, one `<li>` per story:

```html
<li>
  <a href="STORY LINK">HEADLINE</a>
  <span class="clip-meta">OUTLET · DATE</span>
</li>
```

- A new story goes at the top of the list. When adding several at once, or a story older than ones already listed, put each in its place by publish date so the newest is first.
- The first time a clip is added, replace the `[Clips coming soon]` placeholder and its comment with the list. Never add the placeholder back while the list has stories in it.
- Escape `&`, `<` and `>` in headlines as HTML entities. Keep curly quotes and apostrophes as they are.
- Leave the styles alone except to add what the list needs, and keep the "Site style" rules in `CLAUDE.md`.

## 4. Push and report

Commit straight to main with a message like `Add clip: <headline>` and push with `git push origin main`.

Then tell Jade, in plain words, for each story: the headline, outlet and date exactly as you added them, and the link. List anything you couldn't add and what you need from her. Say the live site can take a minute or two to update.
