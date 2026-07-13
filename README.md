# Paridhi Garg — Portfolio Website

Personal portfolio for Paridhi Garg, Content & Demand Generation Strategist.

## Live site
Deployed via Netlify — [paridhi-garg.netlify.app](https://paridhi-garg.netlify.app)

## Pages
Each page now has its own real URL (not just a JS tab switch):
- **Home** (`/`) — Hero, stats, what I do, toolkit, sample work preview, contact strip
- **Work** (`/work`) — Project case studies (accordion) + published writing + campaign assets
- **Blog** (`/blog`) — Articles and essays
  - Individual posts get their own URL, e.g. `/blog/why-your-demand-gen-campaign-is-not-working`
- **Contact** (`/contact`) — Email and LinkedIn

## How to update

### Update your email or LinkedIn
Search for `paridhigarg926@gmail.com` or `paridhi-garg-a4660429b` in `index.html` and replace.

### Add a real blog post (with its own URL)
Since each page now has a real URL, adding a post takes a few small steps in `index.html`:

1. **Duplicate the post section.** Find `<!-- BLOG POST 1 ═══ -->` (`<div class="pg" id="pg-post-blog1">`). Copy the whole block, paste it below, and give it a new id, e.g. `pg-post-blog2`. Update the title, meta, and body text inside.

2. **Register the URL.** In the `<script>` section, find the `routes` object near the top and add a line for your new post:
   ```js
   '/blog/your-post-slug': 'post-blog2',
   ```
   Use a short, hyphenated slug based on the title.

3. **Add a page title.** In the same script section, find `pageTitles` and add:
   ```js
   'post-blog2': 'Your Post Title — Paridhi Garg',
   ```

4. **Link to it from the Blog page.** In the `<!-- BLOG PAGE -->` section, find the entry for that post (or turn a "Coming soon" placeholder into a real one) and make it a real link:
   ```html
   <a class="be rv" href="/blog/your-post-slug" onclick="go('post-blog2');return false;" style="cursor:pointer;text-decoration:none;color:inherit">
     <div class="be-num">02</div>
     <div>
       <div class="be-tag">Your Category</div>
       <div class="be-title">Your Article Title</div>
       <div class="be-exc">Short excerpt or description.</div>
     </div>
     <div><span class="be-pill">Jan 2026</span></div>
   </a>
   ```
   The "Back to writing" button inside your new post section can stay as `onclick="go('blog')"` — no change needed there.

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
