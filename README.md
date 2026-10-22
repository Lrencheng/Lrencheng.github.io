# Lil'Log-style Hugo + PaperMod Starter

This starter replicates the **technology stack and general layout**, not the contents or proprietary branding of Lilian Weng's Lil'Log. It is intended for macOS Apple Silicon and GitHub Pages.

## 0. Prerequisites

Install Homebrew (https://brew.sh), then:

```bash
brew install hugo git
hugo version
git --version
```

## 1. Initialize Git and install PaperMod

Unzip this starter, open Terminal in the unzipped folder, and run:

```bash
git init -b main
git submodule add https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```

## 2. Personalize

Edit `hugo.yaml`:

- Replace `YOUR_GITHUB_USERNAME` with your GitHub username.
- Set site `title`, `params.author`, and `params.description`.
- Rewrite the example post and about/research/cv pages.

## 3. Local preview

```bash
hugo server -D
```

Browse http://localhost:1313/ . `-D` shows draft content locally.

## 4. GitHub Pages deployment

Create a **public** repository named `YOUR_GITHUB_USERNAME.github.io` (without initializing it with a README). In its Settings > Pages select Source: GitHub Actions.

From your local starter folder run:

```bash
git add .
git commit -m "Initial research blog"
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/YOUR_GITHUB_USERNAME.github.io.git
git push -u origin main
```

Visit the GitHub Actions tab to check deployment, then visit https://YOUR_GITHUB_USERNAME.github.io/ .

## 5. Regular posting

```bash
hugo new content posts/2026-10-22-second-post/index.md
hugo server -D
# edit your markdown, set draft: false when ready
git add .
git commit -m "Publish a new research note"
git push
```

## Cautions

- Do not put private notes, unreleased data, or secrets into a public GitHub repo, even as drafts.
- Do not add the generated `public/` folder to Git.
- MathJax loads from jsDelivr; if you need **fully offline** mathematical typesetting, self-host MathJax resources instead.
- When cloning the repo on another computer, use `git clone --recurse-submodules`.
- PaperMod is a Git submodule; update intentionally rather than modifying files within `themes/PaperMod`.
- GitHub Actions has a pinned Hugo version. Keep local and CI Hugo versions compatible.
