# BlogFood
- Static site made with https://gohugo.io
- Repository stored at https://github.com/danuts-thegreat/blogfood
- Deployed with [Github Pages](https://pages.github.com/) at https://danuts-thegreat.github.io/blogfood/

# How to use
## Install Hugo (once)
https://gohugo.io/installation/

Note: take the "Extended" version.

For windows:
- Install [VSCode](https://code.visualstudio.com/download) (for terminal and editing site)
- Install [Git for Windows](https://git-scm.com/download/win)
- Add Git to Windows Environment varialbe (Windows > Environment variables > User > Path > Modify > Add > `C:\Program Files\Git\bin`)
- Download [Hugo Extended v0.131.0 for Windows](https://github.com/gohugoio/hugo/releases/download/v0.131.0/hugo_extended_0.131.0_windows-amd64.zip) 
- Extract zip and copy hugo.exe in `%USERPROFILE%\AppData\Local\Microsoft\WindowsApps` (paste this in Windows Explorer URL)
- Open VSCode terminal (VScode > Terminal > New terminal)
- Check Git and Hugo commands are working:
```sh
hugo version
# hugo v0.131.0
git --version
```

## Clone site from github (once)
Generate ssh key and add it to github repo: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

Then clone with:
```sh
# themes are in submodules and must be cloned too (hence the --recurse-submodules)
git --recurse-submodules clone git@github.com:danuts-thegreat/blogfood.git
```
Open VSCode and add site to it: `File > Add Folder to Workspace > BlogFood`

## Create a new post
From terminal in site root directory:
```sh
hugo new content posts/my-second-post/index.md
# edit posts/my-second-post/index.md (in VSCode)
```
Preview site with new post locally:
```sh
hugo server
# or if post is still "draft = true"
hugo server -D
```
Open http://localhost:1313 in web browser.

More: 
- Hugo doc: https://gohugo.io/getting-started/quick-start/#add-content
- Lightbi theme doc: https://github.com/binokochumolvarghese/lightbi-hugo/blob/main/README.md


## Publish online
- set draft = false in post.md file (ex: `posts/my-second-post/index.md`)
- commit all files and push to github repo
```sh
git add . 
git commit -m "my second post"
git push -u origin main

# to refresh GH personal access token:
git remote set-url origin https://danuts-thegreat:<NEW TOKEN>@github.com/danuts-thegreat/blogfood.git
```
- New content will appear online shortly, once the GitHub pages deploy action have completed (progress can be monitored at https://github.com/danuts-thegreat/blogfood/actions)


