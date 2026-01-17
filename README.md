# Hugo Blog on Cloudflare Pages

A free blog built with Hugo and deployed on Cloudflare Pages.

## Features

- **Hugo Static Site Generator** - Fast and flexible
- **PaperMod Theme** - Clean and modern design
- **Cloudflare Pages** - Free hosting with global CDN
- **Git-based Deployment** - Automatic builds on push

## Local Development

### Prerequisites

- Hugo Extended (v0.146.0 or higher)
- Git

### Running Locally

```bash
# Start the Hugo development server
hugo server -D

# Build the site
hugo
```

The site will be available at `http://localhost:1313`

## Deployment to Cloudflare Pages

### Step 1: Push to GitHub

1. Create a new repository on GitHub
2. Add the remote and push:

```bash
git remote add origin git@github.com:y2hhbw/blog.git
git branch -M main
git push -u origin main
```

### Step 2: Connect to Cloudflare Pages

1. Log in to your [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. Go to **Workers & Pages** > **Create application** > **Pages** > **Connect to Git**
3. Select your GitHub repository (`y2hhbw/blog`)
4. Configure the build settings:
   - **Production branch**: `main`
   - **Build command**: `hugo --minify`
   - **Build output directory**: `public`
   - **Environment variables**:
     - `HUGO_VERSION` = `0.146.0` (or your Hugo version)

5. Click **Save and Deploy**

### Step 3: Custom Domain (Optional)

After deployment, you can add a custom domain:

1. Go to your Pages project settings
2. Click **Custom domains**
3. Add your domain and follow the DNS configuration instructions

## Project Structure

```
.
├── archetypes/          # Content templates
├── content/             # Blog posts and pages
│   └── posts/          # Blog posts
├── themes/             # Hugo themes
│   └── PaperMod/       # PaperMod theme (submodule)
├── hugo.toml           # Hugo configuration
└── README.md           # This file
```

## Creating New Posts

```bash
# Create a new post
hugo new content posts/my-new-post.md

# Edit the post and set draft = false when ready to publish
```

## Resources

- [Hugo Documentation](https://gohugo.io/documentation/)
- [PaperMod Theme](https://github.com/adityatelange/hugo-PaperMod)
- [Cloudflare Pages Docs](https://developers.cloudflare.com/pages/)

## License

MIT
