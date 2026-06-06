# Paridhi Garg — Portfolio Website

Personal portfolio for Paridhi Garg, Content & Demand Generation Marketer.

## Live site
Deployed via Netlify — [your-site-name.netlify.app](https://your-site-name.netlify.app)

## Pages
- **Home** — Hero, stats, what I deliver, toolkit, sample work preview, contact strip
- **Work** — Project case studies (accordion) + published articles + campaign assets
- **Blog** — Articles and essays (placeholder, to be updated)
- **Contact** — Email and LinkedIn

## How to update

### Update your email or LinkedIn
Search for `paridhigarg926@gmail.com` or `paridhi-garg-a4660429b` in `index.html` and replace.

### Add a real blog post
In `index.html`, find the `<!-- BLOG PAGE -->` section. Each article follows this pattern:
```html
<div class="be rv">
  <div class="be-num">01</div>
  <div>
    <div class="be-tag">Your Category</div>
    <div class="be-title">Your Article Title</div>
    <div class="be-exc">Short excerpt or description.</div>
  </div>
  <div><span class="be-pill">Jan 2026</span></div>
</div>
```
Replace `be-pill soon` with `be-pill` and change the text from "Coming soon" to the publish date.

### Add a live article link to the Work page
In the `#ac` pane, copy an existing `art-card` block and update the `href`, title, and rank badge.

### Add a case study
In the Work page `proj-list`, copy an existing `.pi` block, give it a new `id` (e.g. `p4`), update the content, and add `toggleP('p4')` to its header's onclick.

## Deploy to Netlify
1. Push this folder to a GitHub repo
2. Go to [netlify.com](https://netlify.com) → Add new site → Import from Git
3. Select the repo — Netlify auto-detects and deploys
4. Set a custom domain under Site settings → Domain management (optional)

## Tech
Plain HTML + CSS + vanilla JS. No build tools, no dependencies, no frameworks.
