---
author: "icarnaghan"
title: "My Migration Experience from WordPress to Hugo"
date: 2025-06-27
categories: 
  - "coding"
tags: 
  - "hugo"
  - "cicd"
  - "wordpress"
description: "How I simplified the deployment process of my Hugo-powered blog using GitHub Actions and GitHub Pages."
---

I started messing around with Hugo a few months ago as I was getting tired of spending $$s and maintaining a WordPress site that has remained fairly static over the years. When I first heard about [Jamstack](https://jamstack.org/) I was interested in finding ways I could leverage it for my own blog. When I first started I ended up managing the release and deployment of new content in a very manual way, making changes, running `hugo` to generate the static site, and then copying the output to a separate repository that served the site via GitHub Pages. While this workflow worked, it quickly became annoying and error-prone, especially when I forgot a step or made minor changes that didn't get properly deployed.

As I've been getting up to speed with Hugo I quickly realized the simplicity and speed of static site generation and found it to be a refreshing change, but it also means taking on a bit more responsibility when it comes to managing things like deployments and builds, which I didn't have to worry about as much with a hosted WordPress Site. That’s where GitHub Actions came into play. I ended up automating the entire build and deployment process using GitHub Actions. If you're using Hugo for your static site (or are thinking of switching to it), this is approach I ended up with to save time and help keep a clean, repeatable workflow every time I needed to update my site.

## The Old Way

Originally, my content lived in one repository — [`carnaghan.com`](https://github.com/icarnaghan/carnaghan.com) — and my public-facing site was deployed via another, [`icarnaghan.github.io`](https://github.com/icarnaghan/icarnaghan.github.io). Every time I made a content update, I’d do the following:

1. Run `hugo` locally to generate the static site.
2. Copy the contents of the `public/` folder to the `icarnaghan.github.io` repo.
3. Commit and push the changes to trigger GitHub Pages to serve the new content.

This approach worked, but it was brittle. It also forced me to maintain two repos and rely on manual copying.

## Moving to a Single Repo

Instead of maintaining two repositories, I decided to simplify. GitHub Pages supports deploying from a `gh-pages` branch within the same repository, so there’s no reason to separate the content and the output. What this meant was that I was able to:

- Keep everything in the `carnaghan.com` repo.
- Use GitHub Actions to automatically build the Hugo site when I push to `main`.
- Push the generated content to a separate `gh-pages` branch, which GitHub Pages will use to serve the site.


## Setting Up GitHub Actions

To get started, I created a new GitHub Actions workflow inside `.github/workflows/deploy.yml`.

```yaml
name: Deploy Hugo site to GitHub Pages

on:
  push:
    branches:
      - main

permissions:
  contents: write

jobs:
  build-deploy:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout source
      uses: actions/checkout@v4

    - name: Setup Hugo
      uses: peaceiris/actions-hugo@v3
      with:
        hugo-version: 'latest'

    - name: Build site
      run: hugo --minify

    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./public
        publish_branch: gh-pages
```

This action is triggered whenever I push to the main branch. It installs Hugo, builds the static site, and deploys the generated files to the gh-pages branch.

A few things to highlight:

- The GITHUB_TOKEN is a special built-in token that GitHub makes available to workflows for interacting with the API (including pushing commits).
- The peaceiris/actions-gh-pages action handles all the logic around committing and pushing the generated site to the correct branch.
- The permissions: contents: write section is necessary to allow the action to push to the gh-pages branch.

### Actions Used

1. [actions/checkout@v4](https://github.com/actions/checkout) - GitHub's official action that checks out your repo code into the workflow runner, used at the start of most workflows. This action clones my repository into the runner (e.g., Ubuntu VM), so the following steps (like hugo build) can access my files.

2. [peaceiris/actions-hugo@v3](https://github.com/peaceiris/actions-hugo) - A community-maintained action that installs Hugo on the runner. This action lets you easily choose Hugo versions (e.g., latest, 0.124.1). It downloads the correct Hugo binary and adds it to the PATH. Finally it prepares the runner for building Hugo content.

3. [peaceiris/actions-gh-pages@v3](https://github.com/peaceiris/actions-gh-pages) - Another action by peaceiris that deploys a static site to GitHub Pages. This essentially automates the git commit + git push to a gh-pages branch:

- Takes a folder (e.g., public/)
- Initializes a Git repo inside that folder (in the runner)
- Commits the contents
- Pushes it to the GitHub repo's gh-pages branch (or another you specify)

In addition, it also handles all the setup and edge cases like clean deploys, keeping commit history clean, and authentication via GITHUB_TOKEN or PAT.

## Configuring GitHub Pages
Once the workflow is in place, I went to the repository settings on GitHub:

1. Navigate to Settings → Pages.
2. Set the source to gh-pages branch, root (/) folder.

Any time I now push to main, GitHub Actions builds the site and updates what’s served via GitHub Pages — no manual intervention required.

## Dealing with Hugo Warnings

One of the things I needed to do was test the deployment and I quickly found that due to the way I had installed the PaperMod theme as a submodule, github actions was not pulling all the theme code correctly and caused several errors. For Hugo themes I recommend pulling down the code and committing it directly, there is probably a better way to manage this as I'll need to periodically update this theme.

## Final Thoughts

By consolidating my content and deployment into a single repository and leveraging GitHub Actions, I’ve been able to streamline my blogging workflow significantly. I no longer have to think about whether I remembered to copy files or push the right repo — it all just happens automatically on every commit.

If you're managing a Hugo site (or thinking about spinning one up), I highly recommend taking advantage of GitHub Actions Gitlab CI. It simplifies the process and lets you focus on content, not deployment. 

Overall I have been extremely happy with my switch over to Hugo. Special thanks to [Sebastien Taggart](https://www.sebastientaggart.com/) for all the tips in getting me started with Hugo!