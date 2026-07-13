# Paridhi Garg — Portfolio Website

Personal portfolio for Paridhi Garg, Content & Demand Generation Strategist.

## Live site
Deployed via Netlify — [paridhi-garg.netlify.app](https://paridhi-garg.netlify.app)

## Structure
```
/index.html                              — Home, Work, Blog listing, Contact (single-page app)
/style.css                               — shared styles for every page, including blog posts
/blog/why-your-demand-gen-campaign-is-not-working/index.html   — a real, standalone post
/blog/post-template/index.html           — copy this to start a new post
/netlify.toml                            — routing config
```

Home, Work, Blog (the listing), and Contact live together in `index.html` as a single-page app — clicking between them updates the URL (`/`, `/work`, `/blog`, `/contact`) without a full page reload.

**Individual blog posts are separate, standalone HTML files.** Each one lives in its own folder under `/blog/` and is a real page Netlify serves directly at that URL — it doesn't touch or depend on `index.html`'s routing code. This means:
- Adding a post never requires editing `index.html`'s JavaScript
- Each post can have its own page title and social-sharing preview (title/description shown when linked on LinkedIn, etc.)
- All posts and the main site share one `style.css`, so the look stays consistent and can be updated in one place

## Pages
- **Home** (`/`) — Hero, stats, what I do, toolkit, sample work preview, contact strip
- **Work** (`/work`) — Project case studies (accordion) + published writing + campaign assets
- **Blog** (`/blog`) — Listing of articles and essays
  - Each post is its own page, e.g. `/blog/why-your-demand-gen-campaign-is-not-working/`
- **Contact** (`/contact`) — Email and LinkedIn

## How to update

### Update your email or LinkedIn
Search for `paridhigarg926@gmail.com` or `paridhi-garg-a4660429b` in `index.html`, and in each blog post file under `/blog/`, and replace.

### Add a new blog post
No more editing `index.html`'s JavaScript. Just:

1. **Duplicate the template folder.** Copy `/blog/post-template/` and rename the copy to your post's slug, e.g. `/blog/how-i-think-about-content-calendars/`.

2. **Fill in the content.** Open the `index.html` inside your new folder and replace every `[PLACEHOLDER]`:
   - Page `<title>` and `<meta name="description">`
   - The Open Graph tags (`og:title`, `og:description`, `og:url` — update the URL to match your new folder path)
   - The post tag, title, date, read time, and body content
   - Delete the template comment block at the top once you're done

3. **Link to it from the Blog page.** In `index.html` (the main site file), find the `<!-- BLOG PAGE -->` section and either edit an existing "Coming soon" entry or copy the pattern below:
   ```html
   <a class="be rv" href="/blog/your-post-slug/" style="cursor:pointer;text-decoration:none;color:inherit">
     <div class="be-num">02</div>
     <div>
       <div class="be-tag">Your Category</div>
       <div class="be-title">Your Article Title</div>
       <div class="be-exc">Short excerpt or description.</div>
     </div>
     <div><span class="be-pill">Jan 2026</span></div>
   </a>
   ```
   Note the trailing slash in the `href` — keep it, it matches how the post's folder is structured.

That's it — no routes to register, no scripts to touch.

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
