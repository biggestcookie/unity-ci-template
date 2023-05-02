# Unity Game.CI Template

This repo contains a GitHub Actions folder with premade [GameCI](https://game.ci) actions for building a Unity project for Windows 64-bit, MacOS, and WebGL. In addition, the `build-desktop` workflow is configured to create a release with your build files as well as automatically delete build artifacts after the release is created (both to combat GitHub's limited free artifact storage quota -- release uploads do not count towards the quota).

Feel free to this GitHub template when creating your repo, or copy this repo as a `.zip` then copy the included `.github` folder to your own project.

## Setup

1. You will need to follow the [GameCI instructions for activating Unity](https://game.ci/docs/github/activation) with your GitHub repo or org.
2. Consider uncommenting the `push` condition at the top of both `build-desktop.yml` and `build-webgl.yml` if you want GitHub actions to automatically build and release upon changes and merges to your main branch.
   - For billing reference, our Mac and Windows builds take about 5-10 minutes each, while WebGL can often take anywhere between 20-40 minutes. Historically, with several releases per month, we have hardly gotten close to hitting the monthly free tier quota of 2000 minutes.
   - The first runs on any build workflow will take longer than the above estimates, but consequent runs will be much shorter thanks to GitHub caching the created Unity library.
   - If you are often pushing straight to your `main` branch (shame on you), you may not want the automatic building behavior. The workflows also provide a manual workflow trigger you can run whenever you choose.
3. Also consider changing the `projectName` variable in `build-desktop.yml` to your own project name.

## Further reading

https://game.ci/docs/
