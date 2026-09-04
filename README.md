# RefGuard project website

Static project page for **RefGuard: Identity-Aware Language-Guided Robot Manipulation via Joint Target-Anchor-Frame Grounding**.

Everything is plain HTML/CSS/JS with no build step, so it can be served directly by GitHub Pages.

## Files

```
website/
├── index.html            # the whole page (content, styles, and a small script)
├── static/images/        # figures from the paper + video poster frame
├── .nojekyll             # tells GitHub Pages to serve files as-is
└── README.md
```

## 1. Fill in the links

Open `index.html` and edit the `LINKS` block near the bottom of the file:

```js
const LINKS = {
  arxiv:     "",   // e.g. "https://arxiv.org/abs/2609.xxxxx"
  github:    "",   // e.g. "https://github.com/<user>/RefGuard"
  youtubeId: "",   // the ID after "v=" in the YouTube URL, e.g. "dQw4w9WgXcQ"
};
```

Buttons whose link is still empty are shown as "coming soon" automatically, and the
video block shows the poster image with a "coming soon" label until `youtubeId` is set.

## 2. Deploy on GitHub Pages

Option A, dedicated repository (recommended):

1. Create a new public repository, e.g. `RefGuard` (or `refguard-website`).
2. Copy the *contents* of this `website/` folder to the repository root and push.
3. On GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch**,
   branch `main`, folder `/ (root)`, then **Save**.
4. After a minute the site is live at `https://<user>.github.io/RefGuard/`.

Option B, inside the code repository:

1. Copy this folder to `docs/` in the code repository and push.
2. **Settings → Pages**, branch `main`, folder `/docs`.

All asset paths are relative, so the page works both at a domain root and under a
sub-path such as `/RefGuard/`.

## 3. Optional polish

- Social preview: once the site URL is known, set the `og:image` meta tag in
  `index.html` to the absolute URL of `static/images/teaser.jpg`.
- Custom domain: add a `CNAME` file containing the domain and configure DNS.

## Local preview

```bash
cd website && python3 -m http.server 8000
```

Then open <http://localhost:8000>.
