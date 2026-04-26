# Christopher Cato - Personal Website

A clean, minimal, static personal website built with plain HTML and CSS. No build tools, no frameworks, just fast, semantic markup.

## Project Structure

```
christophercato.se/
├── index.html      # Main page with semantic HTML structure
├── styles.css      # Minimal, responsive CSS with dark mode support
├── about_me.md     # Source content (for reference)
└── README.md       # This file
```

## Features

- **Static & Fast**: Pure HTML/CSS, no build process
- **Responsive**: Mobile-first design with CSS Grid
- **Dark Mode**: Automatic dark mode based on system preference
- **SEO Optimized**: Meta tags, Open Graph, Twitter Cards
- **Accessible**: Semantic HTML, proper heading hierarchy
- **Typography-focused**: Clean, professional design

## Running Locally

### Option 1: Python Simple HTTP Server

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000 in your browser.

### Option 2: Node.js http-server

```bash
npx http-server -p 8000
```

Then open http://localhost:8000 in your browser.

### Option 3: VS Code Live Server

If using VS Code, install the "Live Server" extension and click "Go Live".

## Deployment

### Cloudflare Pages

Cloudflare Pages is recommended for its global CDN and automatic HTTPS.

#### Steps:

1. **Push to GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/yourusername/christophercato.se.git
   git push -u origin main
   ```

2. **Connect to Cloudflare Pages**
   - Go to https://dash.cloudflare.com/
   - Navigate to Workers & Pages → Create application → Pages
   - Select "Connect to Git"
   - Choose your repository
   - Build settings (leave empty for static HTML):
     - **Build command**: (empty)
     - **Build output directory**: `/` (root)
   - Click "Save and Deploy"

3. **Add Custom Domain**
   - In Cloudflare Pages dashboard, go to Custom Domains
   - Click "Set up a custom domain"
   - Enter: `christophercato.se`
   - Cloudflare will automatically configure DNS

4. **Update DNS Records**
   - If your domain is registered elsewhere, update DNS to point to Cloudflare:
     - Add CNAME: `christophercato.se` → your-pages-domain.pages.dev
     - Or A record pointing to Cloudflare IPs (if using Cloudflare as DNS provider)

### GitHub Pages

#### Steps:

1. **Push to GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/yourusername/christophercato.se.git
   git push -u origin main
   ```

2. **Enable GitHub Pages**
   - Go to your repository on GitHub
   - Navigate to Settings → Pages
   - Under "Build and deployment", select:
     - **Source**: Deploy from a branch
     - **Branch**: `main`
     - **Folder**: `/` (root)
   - Click Save

3. **Add CNAME File** (for custom domain)
   - Create a file named `CNAME` in the root directory with:
     ```
     christophercato.se
     ```
   - Commit and push:
     ```bash
     git add CNAME
     git commit -m "Add CNAME for custom domain"
     git push
     ```

4. **Configure DNS**
   - Go to your domain registrar's DNS settings
   - Add a CNAME record:
     - **Name/Host**: `@` or `www`
     - **Value**: `yourusername.github.io`
   - DNS propagation may take 5-60 minutes

## Connecting Custom Domain (christophercato.se)

### Using Cloudflare (Recommended)

1. **Transfer or connect domain to Cloudflare**
   - Sign up at https://dash.cloudflare.com/sign-up
   - Add your domain `christophercato.se`
   - Cloudflare will scan existing DNS records
   - Update nameservers at your registrar to Cloudflare's nameservers

2. **Configure DNS**
   - In Cloudflare DNS, add:
     - CNAME: `@` → `your-pages-domain.pages.dev` (for Cloudflare Pages)
     - Or CNAME: `@` → `yourusername.github.io` (for GitHub Pages)

3. **Enable SSL/TLS**
   - Go to SSL/TLS → Overview
   - Set to "Full" or "Full (strict)"
   - Cloudflare will issue a free SSL certificate automatically

### Without Cloudflare

1. **Go to your domain registrar** (e.g., Namecheap, GoDaddy, etc.)
2. **Add CNAME record**:
   - **Type**: CNAME
   - **Name/Host**: `@` or `www`
   - **Value**: `your-pages-domain.pages.dev` (Cloudflare) or `yourusername.github.io` (GitHub)
3. **Wait for DNS propagation** (5-60 minutes)
4. **SSL certificate**: Most platforms provide free SSL (Let's Encrypt) automatically

## Customization

### Update Contact Info

Edit `index.html`, find the contact placeholder in the footer:
```html
<p class="contact-placeholder">Contact: [Your email placeholder]</p>
```

Replace with your actual email:
```html
<p class="contact-placeholder">Contact: <a href="mailto:your@email.com">your@email.com</a></p>
```

### Update Colors

Edit `styles.css`, modify the CSS variables at the top:
```css
:root {
    --accent: #2563eb;  /* Change accent color */
    /* ... other variables */
}
```

### Update Content

Edit `index.html` directly. The content is organized in semantic sections:
- Hero (name + subtitle)
- About section
- Strengths section
- Technologies section

## Performance

The site is optimized for performance:
- **No JavaScript** (except for dynamic year in footer)
- **No external dependencies**
- **Minimal CSS** (single file, ~3KB)
- **Semantic HTML** for better parsing
- **System fonts** for fastest render time

## License

Personal website content. All rights reserved.
