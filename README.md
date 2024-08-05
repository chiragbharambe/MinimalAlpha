# Hugo MinimalAlpha

## Keep it stupid simple

MinimalAlpha is a Hugo theme created by [Chirag Bharambe](https://bharam.be). This theme is built from scratch with a minimal approach, inspired by Xmin and Tokiwa themes. It's incredibly lightweight, with only about 200 lines of code including empty lines.

Key features:
- Dynamic layouts for desktop and mobile
- Full-site search using Pagefind
- Future plans for additional color styles

The theme consists of just a few files:

```bash
find . -type f \( -name "*.html" -o -name "*.css" \) -exec wc -l {} +
  28 ./layouts/_default/list.html
   8 ./layouts/_default/single.html
   7 ./layouts/_default/terms.html
  48 ./layouts/_default/baseof.html
   8 ./layouts/partials/displaytags.html
  96 ./static/css/style.css
 195 total

```

For local development and deployment, add these functions to your .bashrc or .zshrc:

```bash
# Local development
function hls()
{
    cd ~/Projects/bharam.be/ && \
    rm -rf public && \
    hugo && \
    npx pagefind --site "public" &&\
    hugo serve
}

# Deployment
function hvp()
{
    cd ~/Projects/bharam.be/ && \
    rm -rf public && \
    hugo && \
    npx pagefind --site "public" &&\
    vercel --prod
}
```

Use `hls` for local development and `hvp` for deployment.

