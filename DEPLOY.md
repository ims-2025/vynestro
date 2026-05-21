# Going live — GitHub + Vercel

The repo is already initialized locally with an initial commit. Three remaining steps: create the GitHub repo, push, connect Vercel, point the domain.

## 1. Create the GitHub repository

Go to https://github.com/new and create a new repository:

- **Name:** `vynestro-site` (or whatever you prefer)
- **Visibility:** Private is fine — Vercel works with private repos
- **Do NOT** initialize with README, .gitignore, or license (we already have them)

Click "Create repository". On the next screen, copy the SSH or HTTPS URL.

## 2. Push the local repo

Open Terminal on your Mac and run:

```bash
cd "/Users/cg/Documents/Claude/Projects/General Websites/vynestro-site"

# Replace with the URL GitHub showed you (SSH preferred if you have keys set up)
git remote add origin git@github.com:YOUR_USERNAME/vynestro-site.git

git push -u origin main
```

If you get an SSH error, use the HTTPS URL instead: `https://github.com/YOUR_USERNAME/vynestro-site.git` — GitHub will prompt for a Personal Access Token (create one at https://github.com/settings/tokens).

## 3. Connect Vercel

1. Go to https://vercel.com/new
2. Sign in with GitHub if you haven't already, and authorize Vercel to read your repos
3. Find `vynestro-site` in the list and click **Import**
4. Framework preset: **Other** (it's static HTML — no build needed)
5. Leave Build Command, Output Directory, and Install Command blank
6. Click **Deploy**

Vercel will build and deploy in ~30 seconds. You'll get a URL like `vynestro-site-xyz.vercel.app`.

## 4. Point vynestro.com at Vercel

In your Vercel project:

1. Open the project → **Settings** → **Domains**
2. Add `vynestro.com` and `www.vynestro.com`
3. Vercel will show you DNS records to add at your domain registrar — typically:
   - An `A` record for `vynestro.com` → `76.76.21.21`
   - A `CNAME` for `www` → `cname.vercel-dns.com`
4. Add those records at your registrar (GoDaddy, Namecheap, Cloudflare, etc.)
5. SSL provisions automatically once DNS propagates (usually 5–30 minutes)

## Future updates

Edit `index.html`, then:

```bash
cd "/Users/cg/Documents/Claude/Projects/General Websites/vynestro-site"
git add -A
git commit -m "Update hero copy"
git push
```

Vercel auto-deploys every push to `main`. Done.

## Optional next steps

- **Lead capture** — the contact form currently only animates a "sent" state. To actually receive submissions, plug in Formspree (free tier), Resend, or convert the form to a Vercel Serverless Function.
- **Analytics** — Vercel Analytics is one toggle in the project dashboard.
- **Favicon** — add a `favicon.ico` or `favicon.svg` to the root of the repo.
- **Open Graph image** — add an `og-image.png` (1200×630) and a `<meta property="og:image">` tag for link previews.
