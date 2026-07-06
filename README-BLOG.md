# Field Notes — Setup & Publishing Guide

No coding required after setup. Publishing a note = creating one text file on github.com.

---

## One-time setup (about 10 minutes)

1. **Copy these into your website's GitHub repository** (the same repo that serves ronniebailey.cloud):
   - `blog.html` and `post.html` → into the root of the repo, next to `index.html`
   - the `posts` folder (including `_template.md` and the example post) → into the root of the repo

2. **Edit the config in TWO files.** Open `blog.html` and `post.html` on github.com (pencil icon), find the block near the bottom that looks like this, and fill in your details in both files:

   ```
   const BLOG_CONFIG = {
       owner:    "YOUR-GITHUB-USERNAME",
       repo:     "YOUR-REPO-NAME",
       branch:   "main",
       postsDir: "posts"
   };
   ```

   Example: if your site lives at `github.com/ronnieblog/ronnieblog.github.io`, then owner is `ronnieblog` and repo is `ronnieblog.github.io`. If your default branch is `master` instead of `main`, change that too.

3. **Add the nav link to your portfolio.** In `index.html`, find the nav and add one line:

   ```
   <a href="blog.html">Field Notes</a>
   ```

4. Commit. Give GitHub Pages a minute to publish, then visit `yoursite.com/blog.html`.

> Note: the pages load posts from GitHub's servers, so they only work on the live site — opening `blog.html` by double-clicking the file on your Mac will show an error. That's expected.

---

## Publishing a new note (2 minutes, works from your phone)

1. On github.com, open the `posts` folder → **Add file → Create new file**.
2. Name it with the date first: `2026-07-15-my-note-title.md` (the date prefix keeps everything sorted; lowercase words separated by dashes).
3. Open `_template.md` in another tab, copy its front matter block (the part between the `---` lines), paste it in, and fill in your title, date, tags, and summary.
4. Write the note below the second `---` in plain Markdown.
5. **Commit.** It appears on the front page immediately, newest first. The tag cloud updates itself.

Delete a note's file and it disappears from the site. No index to maintain anywhere.

## Banners: images, GIFs, and video

1. Upload the media file to `posts/assets/` (open that folder → **Add file → Upload files**).
2. Reference it in the note's front matter:

   ```
   banner: posts/assets/richmond-bsides-2026.jpg
   ```

   - `.jpg` / `.png` → shows as an image
   - `.gif` → animates automatically
   - `.mp4` / `.webm` → autoplays muted and loops (with controls on the article page) — good for conference or event clips
   - A full `https://` URL also works
   - No `banner:` line → the card shows a clean placeholder icon instead. Totally fine.

On the front page the banner is a small fixed-size thumbnail; on the article page it runs the full content width at its natural shape (capped so a tall image doesn't take over the screen).

**Keep video banners small** — under ~15 MB. GitHub isn't a video host; for anything longer than a short clip, upload it to your Cloudflare R2 bucket (same setup as Freedmen Star) and use the full URL.

## Tags

Comma-separated in the front matter: `tags: identity, zero-trust, pam`. The sidebar cloud sizes each tag by how often it appears and clicking one filters the front page. Discipline matters more than the feature: pick 5–8 recurring tags and stick to them.

## Things to know

- Files starting with `_` (like `_template.md`) never appear on the site.
- If the front page says it can't load: 99% of the time the owner/repo values in the config don't match your repo, or the branch is wrong.
- The example post (`2026-07-05-deprovisioning...`) is real enough to keep, but read it first — edit or replace it so the voice is fully yours before you share the link.
