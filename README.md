# Onell Aquino personal site

Local Jekyll + Minima site styled after [joekoshakow.com](https://joekoshakow.com/).
GitHub publish is left to you (see below).

## Preview locally

```bash
export PATH="/opt/homebrew/opt/ruby/bin:/opt/homebrew/lib/ruby/gems/4.0.0/bin:$PATH"
cd ~/Desktop/dev/aquinoonell.github.io
bundle exec jekyll serve
```

Open http://127.0.0.1:4000

## Publish to GitHub Pages (your steps)

Repo name must be exactly `aquinoonell.github.io` for the user site URL.

### 1. Commit locally

```bash
cd ~/Desktop/dev/aquinoonell.github.io
git status
git add .
git commit -m "$(cat <<'EOF'
Add personal site for GitHub Pages.

EOF
)"
```

(If git is not initialized yet: `git init && git branch -M main` first.)

### 2. Create the remote repo and push

```bash
gh repo create aquinoonell/aquinoonell.github.io --public --source=. --remote=origin --push
```

If the empty repo already exists on GitHub:

```bash
git remote add origin https://github.com/aquinoonell/aquinoonell.github.io.git
git push -u origin main
```

### 3. Enable GitHub Pages

1. Open https://github.com/aquinoonell/aquinoonell.github.io/settings/pages
2. Under **Build and deployment**, set Source to **Deploy from a branch**
3. Branch: `main` / folder `/ (root)` → Save  
   (Or use the **GitHub Actions** Jekyll workflow if GitHub suggests it.)
4. Wait 1–2 minutes, then open https://aquinoonell.github.io

### 4. Optional follow ups

- GitHub profile → set **Website** to `https://aquinoonell.github.io`
- Pin featured repos that match the Projects page
- Custom domain later: Pages → Custom domain + DNS

## Layout notes

Content width is ~1000px (wider than stock Minima 800px) with 18px body text.
Edit `assets/main.scss` (`$content-width`, `$base-font-size`) to tune further.
