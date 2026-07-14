# DCSPitHIDC — Website

Fast, clean marketing site for DCSPitHIDC. Hosted free on Cloudflare Pages.

## What's Included

- `index.html` — Complete single-page website with all sections
- `README.md` — This file
- `.gitignore` — Git configuration

## Deploy to Cloudflare Pages (5 minutes)

### 1. Create a GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Name it `dcspit-website` (or whatever you like)
3. Public repo
4. **Do not** add a .gitignore or README yet (you already have these files)
5. Click "Create repository"

### 2. Push Your Files to GitHub

Once the repo is created, GitHub will show you commands. Run these in your terminal:

```bash
git init
git add .
git commit -m "Initial commit - DCSPitHIDC website"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/dcspit-website.git
git push -u origin main
```

(Replace `YOUR_USERNAME` with your actual GitHub username, and `dcspit-website` with your repo name if different.)

### 3. Connect to Cloudflare Pages

1. Go to [dash.cloudflare.com](https://dash.cloudflare.com)
2. Sign up (free) if you don't have an account
3. Click **Pages** in the left sidebar
4. Click **"Create a project"**
5. Select **"Connect to Git"**
6. Authorize GitHub and select your new repository
7. **Build settings:**
   - Framework: `None` (this is plain HTML)
   - Build command: (leave blank)
   - Build output directory: (leave blank)
8. Click **"Save and Deploy"**

Done. Your site is live at `dcspit-website.pages.dev` (or whatever your repo name is).

### 4. (Optional) Use Your Own Domain

To use a custom domain like `dcspit.com`:

1. In Cloudflare, go to **Pages** → Your project → **Settings** → **Domains**
2. Click **"Add a domain"**
3. Enter your domain and follow the prompts
4. Cloudflare will give you nameserver instructions — update your domain registrar

## Making Changes

Every time you push to `main` on GitHub, Cloudflare automatically redeploys. So:

```bash
# Edit index.html locally
nano index.html

# Commit and push
git add .
git commit -m "Update: add videos section"
git push
```

Your site updates within 60 seconds.

## Editing the Website

Open `index.html` in any text editor. Key sections to customize:

| Section | What to Edit |
|---------|---|
| **Navigation links** | Line ~170 (`<nav>`) |
| **Hero text** | Lines ~180–185 |
| **Pricing** | Lines ~600–620 |
| **Resources links** | Lines ~628–652 (Icedrive/YouTube links go here) |
| **Footer** | Lines ~680–690 |
| **Colors** | Lines ~17–23 (CSS variables) |

### Adding Videos

In the **Resources & Media** section (around line 632), replace the placeholder text with embedded YouTube:

```html
<div class="media-item">
  <h4>Setup Tutorial</h4>
  <iframe width="100%" height="200" src="https://www.youtube.com/embed/VIDEO_ID" 
    frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
    allowfullscreen></iframe>
</div>
```

### Adding Icedrive Links

```html
<a href="https://icedrive.net/s/YOUR_SHARE_LINK">Download PDF</a>
```

### Buy Button Link

Line ~670, replace the `onclick="alert..."` with your actual link:

```html
<a href="https://checkout.stripe.com/..." class="cta-button">Buy Now</a>
```

## Brand Colors

The site uses the official DCSPIT brand:

- **Navy**: `#0b1a2e` (background, headers, text accents)
- **Amber**: `#f0a94c` (accents, highlights, buttons)
- **White**: `#ffffff` (body)
- **Light Gray**: `#f5f5f5` (cards, sections)

These are defined as CSS variables at the top of the file — easy to tweak.

## Performance

The site is **fast by default**:
- Single HTML file, no external requests (except fonts from system)
- No JavaScript libraries or frameworks
- Cloudflare CDN caches it globally
- Mobile responsive

Load time: < 100ms globally.

## What's TBD

- **Buy button**: Link to your Stripe store, Gumroad, or other payment method
- **PDF links**: Icedrive or direct links to the Builder, Trade, and Spec PDFs
- **Video links**: YouTube or embedded tutorial videos
- **Contact/Support**: Email or contact form link in footer

Just update the `onclick="alert(...)"` lines and placeholder links as you finalize those.

## Questions?

- Cloudflare Pages docs: [pages.cloudflare.com](https://pages.cloudflare.com)
- GitHub help: [docs.github.com](https://docs.github.com)

---

**Built for speed. Deploy once, update anytime.**
