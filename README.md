# GHP Labs Website

Company landing page and legal documents for GHP Labs LLC products.

## Structure

```
/
├── index.html          # Main landing page
├── styles.css          # Shared styles
├── CNAME               # Custom domain config
│
└── clipcook/
    ├── privacy.html    # ClipCook Privacy Policy
    └── terms.html      # ClipCook Terms of Service
```

## Deployment

This site is deployed via GitHub Pages.

### Setup (One-time)

1. Create a new GitHub repository named `ghplabs-website`
2. Push this code to the repository
3. Go to **Settings** > **Pages**
4. Under "Source", select **Deploy from a branch** and choose `main`
5. The site will be available at `https://your-username.github.io/ghplabs-website`

### Custom Domain (ghplabs.ai)

1. In your domain registrar (e.g., Namecheap, GoDaddy), add these DNS records:
   - **A Record:** `@` → `185.199.108.153`
   - **A Record:** `@` → `185.199.109.153`
   - **A Record:** `@` → `185.199.110.153`
   - **A Record:** `@` → `185.199.111.153`
   - **CNAME Record:** `www` → `your-username.github.io`

2. In GitHub repo **Settings** > **Pages**, enter `ghplabs.ai` as the custom domain
3. Enable "Enforce HTTPS"

DNS propagation may take up to 24 hours.

## Adding a New App

1. Create a new folder: `new-app-name/`
2. Add `privacy.html` and `terms.html` (copy from clipcook and modify)
3. Add a new app card to `index.html`

## Local Development

Just open `index.html` in a browser. No build step required.
