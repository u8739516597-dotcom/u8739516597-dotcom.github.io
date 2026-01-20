VR Locomotion Blog (Lab 1)



Author: Peiwen Zhang (张佩文)

Program: Université Paris-Saclay, HCI M1

Course: Human-Computer Interaction for Mixed Reality

Lab: Lab 1 (Hugo + GitHub Pages)



Blog Website (Most Important)



Live site: https://u8739516597-dotcom.github.io/
This README is for Lab 1 setup. All future assignments will be documented as blog posts in content/posts.



What this repository contains



This repository includes:



Hugo source files (blog content and configuration): content/, themes/, hugo.toml



Generated static website for GitHub Pages: docs/



How to run locally



In the repository root folder, run:

hugo server



Then open in browser:

http://localhost:1313/



How to publish (deploy) to GitHub Pages



Step 1: Build the static site into the docs/ folder:

hugo --cleanDestinationDir



Step 2: Commit and push:

git add .

git commit -m "Update site"

git push



GitHub Pages settings used in this project:



Branch: main



Folder: /docs



Problems I met and how I fixed them



git push error 403 (permission denied)

Problem: Git was using credentials from another GitHub account, so push was denied.

Fix: Removed the old GitHub credentials in Windows Credential Manager, then authenticated again in the browser and pushed successfully.



CSS not applied on GitHub Pages (style missing)

Problem: The site loaded without PaperMod styles (CSS not applied).

Fix: Disabled fingerprinting/SRI in Hugo, rebuilt the site, then deployed again.



Config change in hugo.toml:

\[params.assets]

disableFingerprinting = true

