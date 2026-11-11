# jaisite — jaigandhi.life

Jai's personal site: Jekyll (Lanyon theme) on GitHub Pages, legacy build from `master:/`. Domain at GoDaddy (GoDaddy nameservers; apex A records → GitHub Pages IPs, `www` CNAME → `gandhiprep.github.io`).

- **Pushing `master` publishes the live site.** Work on a branch and merge only when Jai asked for that change to go live. Never force-push; `git fetch` first.
- Don't change DNS, the `CNAME` file, or Pages settings without an explicit request. The HTTPS certificate is GitHub-managed and auto-renews.
- `/socialclub/` (titled "Tapestry") is a chronological events feed, newest first, no pagination. It is not the Tapestry app; don't host the app's privacy policy here unless Jai says so.
- One `_posts/YYYY-MM-DD-slug.md` per event: top text, photo/video, bottom text, in Jai's own words. Use `{% include event-image.html %}` / `{% include event-video.html %}` (they render nothing if the file is missing), never a hardcoded `<img>` for media that may not exist.
- Shot on iPhone (`_data/photos.yml`) shows location only, no dates. Strip EXIF and fix orientation before adding photos.
- Copy changes come from Jai (text, or the Notion page "jaigandhi.life — site copy"); don't rewrite Jai's wording beyond what Jai asked.
- After a push, check `gh api repos/gandhiprep/jaisite/pages/builds/latest` reaches `built`, then fetch the live page.
