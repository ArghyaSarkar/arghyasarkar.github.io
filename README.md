# Personal site — Arghya Sarkar

Static, self-contained personal site. Two pages (`index.html` = Profile, `writing.html` = Writing), shared `styles.css` + `app.js`. No build step, no dependencies, no framework — deploys anywhere that serves static files.

## Preview locally (fully private, no hosting)
Just open the file in a browser:
```
open index.html
```
Everything works offline — system fonts, light/dark (follows your OS), responsive.

## Publish on GitHub Pages — when you're ready

> Keep the repo **private** while drafting. GitHub Pages from a *private* repo needs GitHub **Pro**; on the free plan, make the repo **public** at publish time. Either way, nothing in these files changes.

1. Create a **private** repo on your **personal** GitHub account (not a work org).
2. Push:
   ```
   git init
   git add .
   git commit -m "Personal site"
   git branch -M main
   git remote add origin git@github.com:<your-personal-username>/<repo>.git
   git push -u origin main
   ```
3. When ready to go live: **Settings → Pages → Build from branch → `main` / root**. Site appears at `https://<username>.github.io/<repo>/`.

## Custom domain — add any time later
1. **Settings → Pages → Custom domain** → enter your domain (writes a `CNAME` file).
2. At your registrar's DNS (any registrar — GoDaddy, Cloudflare, Namecheap…):
   - apex → four `A` records to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - or `www`/subdomain → `CNAME` to `<username>.github.io`
3. **Verify a domain** (account Settings → Pages) with the `TXT` challenge — prevents hijacking.
4. Tick **Enforce HTTPS** (free auto cert).

## Notes
- `.nojekyll` disables Jekyll so any `_`-prefixed files are served untouched.
- Fonts are system stacks (render from the visitor's OS). To swap in a self-hosted webfont later, add the files + `@font-face` in `styles.css`.
