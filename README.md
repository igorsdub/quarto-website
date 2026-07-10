# Quarto Website Template for GitHub Pages

Use this public template to create your own Quarto website and publish it with GitHub Pages.

This repository is set up as a simple Quarto website project with:

- Quarto site configuration in [`_quarto.yml`](/Users/igorsdubanevics/projects/quarto-website/_quarto.yml)
- Page content in `.qmd` files such as [`index.qmd`](/Users/igorsdubanevics/projects/quarto-website/index.qmd) and [`about.qmd`](/Users/igorsdubanevics/projects/quarto-website/about.qmd)
- A GitHub Actions workflow in [`.github/workflows/publish.yml`](/Users/igorsdubanevics/projects/quarto-website/.github/workflows/publish.yml)

## Quick Start

### 1. Create your own repository from this template

The simplest option is to click **Use this template** on GitHub, create your own repository, and then clone it to your machine.

**Note** The website build will first fail and you will probably recevie an email from GitHub. Worry not! We solve this issue in the next section.

```text
ERROR: Unable to publish to GitHub Pages (the remote origin does not have a branch named "gh-pages". Use first `quarto publish gh-pages` locally to initialize the remote repository for publishing.)
```

If you want to do it from the command line with GitHub CLI, you can create a new repository from this template and clone it in one step:

```bash
gh repo create YOUR-USERNAME/YOUR-REPO --public --template OWNER/TEMPLATE-REPO --clone
```

For standard GitHub Pages usage, make the repository public. If you are working inside an organization, an internal repository may also be an option depending on your organization's GitHub plan and Pages settings.

### 2. Publish the site from your local machine

From the root of the repository, publish the site to the `gh-pages` branch:

```bash
quarto publish gh-pages
```

Quarto will render the website, create or update the `gh-pages` branch, and push the published site to GitHub.

You can also build locally first if you want to check the output before publishing:

```bash
quarto preview
```

This command starts a local server in your terminal and automatically opens the rendered website in your default browser. You can live-edit `.qmd` files and see those changes reflected in the website automatically.

### 3. Tell GitHub Pages to use the `gh-pages` branch

After the first publish:

1. Open your repository on GitHub.
2. Go to **Settings** -> **Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select the `gh-pages` branch and the `/(root)` folder.
5. Save.

Once GitHub Pages finishes deploying, your website will be available at its GitHub Pages URL.

See [GitHub Docs for a more visual guide](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-from-a-branch).

### 4. Add the website URL to the repository description

Take the website URL and add it to the repository description or homepage field on GitHub so people can spot and open the live site quickly.

At the GitHub repository page, click **Settings** (gear icon) on the left side from **About**. 

![GitHub repository website about section and website link.](/images/github_about-section.png)

If GitHub Pages are set, then you can click **Use your GitHub Pages website** and **Save Changes**. For additional karma points, add a short description so others and yourself know what this website is about.

![Click **Use your GitHub Pages website** and add description.](image.png)

## For the Detail-Oriented

### Install Quarto

Visit [Quarto Getting Started](https://quarto.org/docs/get-started/) to download the official distribution.

If you prefer terminal installation use `brew` or `apt-get` or whaterver pacakge manager you use.

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

If you created the repository on GitHub first, you can clone it with:

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPO.git
cd YOUR-REPO
```

If you prefer to work mostly with GitHub CLI, `gh` can also help you create, clone, and manage the repository from the terminal.

### GitHub Actions workflow

This template already includes a GitHub Actions workflow at [`.github/workflows/publish.yml`](/Users/igorsdubanevics/projects/quarto-website/.github/workflows/publish.yml). `.github` is a special directory, a la `.git`, that is recognized by GitHub.

That workflow is configured to publish on pushes to `main`, using Quarto's official GitHub Action. It is helpful if you want GitHub to handle rendering and publishing after you push changes.

For this workflow-based approach, it is still useful to do an initial local publish so the GitHub Pages branch and Quarto publish configuration are set up cleanly.

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
