# decibold

Image hosting and operations files for the Decibold Instagram automation.
Instagram (via Metricool) pulls images from commit-pinned raw URLs:
`https://raw.githubusercontent.com/White-Venus-Brands/decibold/<commit-sha>/<path>`

- `assets/cutouts/` real product cutouts (never AI-drawn)
- `assets/brand/` logo and brand files
- `posts/<date-slug>/` feed carousels, `stories/<week>/` daily Stories
- `ops/PLAYBOOK.md` rules every automated run reads first
- `ops/post_log.md`, `ops/ads_log.md`, `ops/feed_used.md` logs
