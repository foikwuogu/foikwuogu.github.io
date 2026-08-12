# Friday Ikwuogu — Academic Website

A personal academic website built on **Jekyll** + the **Minimal Mistakes** theme
(the same theme that powers `jayrobwilliams.com` and the popular
`academicpages` template). It's a static site — no database, no server code —
so it runs free forever on GitHub Pages.

```
_config.yml         → site settings, your name, bio, social links
_data/navigation.yml → the top nav bar (About / Publications / Research / Teaching / CV)
_pages/              → About (home), CV, Publications index, Research, Teaching, 404
_publications/       → one file per paper (shows up on the Publications page)
images/profile.jpg   → your headshot, shown in the sidebar
files/                → put a downloadable CV PDF here if you want one
```

---

## 1. Already personalized

`_config.yml` is set up for GitHub username **foikwuogu** (site URL
`https://foikwuogu.github.io`, repo `foikwuogu/foikwuogu.github.io`), and the
sidebar links point to your real ORCID, Google Scholar, ResearchGate,
LinkedIn, GitHub, email, and phone. Nothing to change here unless these
details change later.

---

## 2. Run it locally

You need **Ruby** and **Bundler** installed once. Then, from this folder:

```bash
gem install bundler
bundle install
bundle exec jekyll serve
```

Open **http://localhost:4000** in your browser. Jekyll watches the files and
rebuilds automatically when you save changes — just refresh the page.

**macOS:** if you don't have Ruby's dev headers, run `xcode-select --install`
first (this also installs Git).
**Windows:** install Ruby via [RubyInstaller](https://rubyinstaller.org/) (pick
the "with DevKit" option), then use Git Bash for the commands above.
**Linux:** install `ruby-full` and `build-essential` via your package manager.

Stop the local server anytime with `Ctrl+C`.

---

## 3. Put it on GitHub Pages (free hosting)

1. Create a **new GitHub repository** named exactly `foikwuogu.github.io`
   (this exact name is what makes GitHub build it into a live website
   automatically).
2. From inside this folder, connect it to that repo and push:

   ```bash
   git init
   git add .
   git commit -m "Initial commit — academic website"
   git branch -M main
   git remote add origin https://github.com/foikwuogu/foikwuogu.github.io.git
   git push -u origin main
   ```

3. On GitHub, go to your repo's **Settings → Pages**, and under "Build and
   deployment" set **Source: Deploy from a branch**, **Branch: main / (root)**.
   Save.
4. Wait a minute or two, then visit **https://foikwuogu.github.io** —
   your site is live.

From then on, any time you edit a file and want the live site to update:

```bash
git add .
git commit -m "describe what you changed"
git push
```

GitHub rebuilds the site automatically within a minute or two of each push.

---

## 4. Adding more content later

* **New publication** → add a new file in `_publications/`, copy the front
  matter pattern from an existing one, change the title/date/venue/citation.
* **New CV entries** → edit `_pages/cv.md` directly (it's plain Markdown with
  `Header\n======` section titles).
* **Downloadable CV PDF** → drop the PDF in `files/`, then uncomment the link
  at the top of `_pages/cv.md` and point it at the filename.
* **Profile photo** → replace `images/profile.jpg` with your own (same
  filename, roughly square works best).
* **Theme color** → change `minimal_mistakes_skin` in `_config.yml` (options:
  `default`, `air`, `aqua`, `contrast`, `dark`, `dirt`, `neon`, `mint`, `plum`,
  `sunrise`).

---

## Custom domain (optional)

If you want `www.yourname.com` instead of `<username>.github.io`, add a `CNAME`
file to the repo root containing just your domain, and point your domain
registrar's DNS at GitHub Pages (GitHub's docs walk through this under
Settings → Pages → Custom domain).
