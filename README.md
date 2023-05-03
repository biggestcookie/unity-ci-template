# Unity Game.CI Template

This repo contains a GitHub Actions folder with premade [GameCI](https://game.ci) actions for building a Unity project for Windows 64-bit, MacOS, and WebGL. 

## Features:
- Automatic [GitHub Pages deployment](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site) for WebGL builds
- Automatic [GitHub releases](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases) for desktop builds
    - and automatic artifact deletion on desktop workflow, to cut down on [GitHub's artifact storage quota](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions#included-storage-and-minutes)

Use this GitHub template when creating your repo, or copy this repo as a `.zip` then copy the included `.github` folder to your own project.

## Setup

1. You will need to follow the [GameCI instructions for activating Unity](https://game.ci/docs/github/activation) with your GitHub repo or org.
2. Consider uncommenting the `push` condition at the top of both `build-desktop.yml` and `build-webgl.yml` if you want GitHub actions to automatically build and release upon changes and merges to your main branch.
   - If you are often pushing straight to your `main` branch (shame on you), you may not want the automatic building behavior. The workflows also provide a manual workflow trigger you can run whenever you choose.
   - For billing reference, our Mac and Windows builds take about 5-10 minutes each, while WebGL can often take anywhere between 20-40 minutes (that comes out to 25-50 releases/deployments per month if doing Mac, Windows, and WebGL). 
   - The first runs on any build workflow will take longer than the above estimates, but consequent runs will be much shorter thanks to GitHub caching the created Unity library.
3. Also consider changing the `projectName` variable in `build-desktop.yml` to your own project name.

## Further reading

https://game.ci/docs/
