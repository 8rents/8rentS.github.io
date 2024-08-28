# ![8rentS Logo](https://raw.githubusercontent.com/8rents/_/i/h1/jimi.png) 8rents.github.io

> *This is the repo that handles hosting for [`https://brenton.holiday`](https://brenton.holiday).*
>
> *The files on this branch will be deployed to GitHub Pages.* 

---

This repository provides hosting for [`https://brenton.holiday`](https://brenton.holiday) on the GitHub pages platform.

The site is deployed to GitHub Pages on the [`live`](https://github.com/8rents/8rentS.github.io/tree/live) branch.

**For further Documentation on this project Please check the [`docs`](https://github.com/8rents/8rentS.github.io/tree/docs) branch.**

## Static site deployment

Currently deployment is being handled by a GitHub Action located on this branch in the 

`.github/workflows/static.yml` 

```yaml
# Simple workflow for deploying static content to GitHub Pages
name: Deploy static content to Pages

on:
  # Runs on pushes targeting the default branch
  push:
    branches: ["live"]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

# Allow only one concurrent deployment, skipping runs queued between the run in-progress and latest queued.
# However, do NOT cancel in-progress runs as we want to allow these production deployments to complete.
concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  # Single deploy job since we're just deploying
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Setup Pages
        uses: actions/configure-pages@v5
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          # Upload entire repository
          path: '.'
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```



---

**🤍 2024 [brenton.holiday](https://brenton.holiday)**
