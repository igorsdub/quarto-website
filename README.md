# Quarto Website Template for GitHub Pages

Use this public template to create your own Quarto website and publish it with GitHub Pages.

This repository is set up as a simple Quarto website project with:

- Quarto site configuration in [`_quarto.yml`](/Users/igorsdubanevics/projects/quarto-website/_quarto.yml)
- Page content in `.qmd` files such as [`index.qmd`](/Users/igorsdubanevics/projects/quarto-website/index.qmd) and [`about.qmd`](/Users/igorsdubanevics/projects/quarto-website/about.qmd)
- A GitHub Actions workflow in [`.github/workflows/publish.yml`](/Users/igorsdubanevics/projects/quarto-website/.github/workflows/publish.yml)

## Quick Start

Create your own repository from this template. If you use the GitHub web UI, make sure to include **all branches** so the `gh-pages` branch comes along.

For standard GitHub Pages usage, make the repository public. If you are working inside an organization, an internal repository may also be an option depending on your organization's GitHub plan and Pages settings.

Your browser should like this
![Creating a repository from a template.](/images/github_using-template.png)

Next, press **Create repository**.
![alt text](/images/github_create-repo-button.png)

GitHub Actions will start it magic and in less then a minute you will have your functional and publically running website.

For extra karma points add the website URL to the repository About section. At the GitHub repository page, click **Settings** (gear icon) on the left side from **About**.

![GitHub repository website about section and website link.](/images/github_about-section.png)

If GitHub Pages are set, then you can click **Use your GitHub Pages website** and **Save Changes**.

![Click **Use your GitHub Pages website** and add description.](/images/github_edit-repo-details.png)

Now, you can clone the repository and do the edits locally. When you will be pushing the website to the GitHub remote, GitHub Action swill automatically build and deploy it to the GitHub Pages.
If you only use vanilla Quarto, then you are good to go. For additianl depdenies you need to update [`.github/workflows/publish.yml`](/Users/igorsdubanevics/projects/quarto-website/.github/workflows/publish.yml).

## For the Detail-Oriented

### Install Quarto (optional)

Visit [Quarto Getting Started](https://quarto.org/docs/get-started/) to download the official distribution.

You only need Quarto locally if you want to preview, render, or publish the site from your machine. If you created the repository from the template and included all branches, GitHub Pages can already build the website without this local setup step.

If you prefer terminal installation, use `brew`, `apt-get`, or whichever package manager you normally use.

On macOS with Homebrew:

```bash
brew install --cask quarto
```

On Ubuntu or Ubuntu in WSL, install the downloaded `.deb` package with `apt`. A common flow is:

```bash
sudo apt-get update
sudo apt-get install ./quarto-amd64.deb
```

After installing, confirm Quarto is available:

```bash
quarto --version
```

### If you did not include all branches

If you create the repository from the template without including all branches, the `gh-pages` branch will not exist yet. In that case, the initial website build can fail until you create that branch locally.

From the root of the repository, run:

```bash
quarto publish gh-pages
```

Quarto will render the website, create or update the `gh-pages` branch, and push the published site to GitHub.

After that, open **Settings** -> **Pages** and confirm GitHub Pages is publishing from the `gh-pages` branch and the `/(root)` folder.

See [GitHub Docs for a more visual guide](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-from-a-branch).

### Useful local commands

Preview the site locally while editing:

```bash
quarto preview
```

Render the site without publishing:

```bash
quarto render
```

### GitHub CLI alternative flow

If you want to create the repository from the command line with GitHub CLI and include all template branches, use:

```bash
gh repo create YOUR-USERNAME/YOUR-REPO --public --template OWNER/TEMPLATE-REPO --include-all-branches --clone
```

If you created the repository on GitHub first, you can clone it with:

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPO.git
cd YOUR-REPO
```

If you prefer to work mostly with GitHub CLI, `gh` can also help you create, clone, and manage the repository from the terminal. The key flag for this template is `--include-all-branches`, since it brings over the prebuilt `gh-pages` branch too.

### GitHub Actions workflow

This template already includes a GitHub Actions workflow at [`.github/workflows/publish.yml`](/Users/igorsdubanevics/projects/quarto-website/.github/workflows/publish.yml). `.github` is a special directory, a la `.git`, that is recognized by GitHub.

That workflow is configured to publish on pushes to `main`, using Quarto's official GitHub Action. It is helpful if you want GitHub to handle rendering and publishing after you push changes.

### Files you will likely edit

- [`_quarto.yml`](/Users/igorsdubanevics/projects/quarto-website/_quarto.yml) for site title, navigation, theme, and global website settings
- [`index.qmd`](/Users/igorsdubanevics/projects/quarto-website/index.qmd) for the homepage
- Other `.qmd` files for additional pages. For example, [`about.qmd`](/Users/igorsdubanevics/projects/quarto-website/about.qmd) is a standard secondary page in many websites. To make it easy to find, include it in the navigation bar or link to it from another page such as [`index.qmd`](/Users/igorsdubanevics/projects/quarto-website/index.qmd).

### Custom domain

If you do not want the default GitHub Pages URL tied to the repository name, you can buy a custom domain and configure GitHub Pages so that domain points to your website.

Check out [GitHub Pages Custom Domain docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages).

## References

- Quarto websites: <https://quarto.org/docs/websites/>
- Quarto publishing to GitHub Pages: <https://quarto.org/docs/publishing/github-pages.html>
- GitHub Pages publishing source: <https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site>
