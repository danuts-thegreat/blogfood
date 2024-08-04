# BlogFood
- Static site made with https://gohugo.io
- Stored in https://github.com/DanutsTheGreat/BlogFood
- Deployed with [Cloudflare Pages](https://pages.cloudflare.com)

## Install Hugo
https://gohugo.io/installation/

For windows:
- Install [VSCode](https://code.visualstudio.com/download) (for terminal and editing site)
- Install [Git for Windows](https://git-scm.com/download/win)
- Add Git to Windows Environment varialbe (Windows > Environment variables > User > Path > Modify > Add > `C:\Program Files\Git\bin`)
- Download [Hugo v0.131.0 for Windows](https://github.com/gohugoio/hugo/releases/download/v0.131.0/hugo_0.131.0_windows-amd64.zip) 
- Extract zip and copy hugo.exe in `%USERPROFILE%\AppData\Local\Microsoft\WindowsApps` (paste this in Windows Explorer URL)
- Open VSCode terminal (VScode > Terminal > New terminal)
- Check Git and Hugo commands are working:
```sh
hugo version
# hugo v0.131.0
git --version
```

## Clone site from github
Generate ssh key and add it to github repo: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account

Then clone with:
```sh
git clone git@github.com:danuts-thegreat/blogfood.git

# add submodule themes
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
git submodule add https://github.com/binokochumolvarghese/lightbi-hugo themes/lightbi-hugo
```
Open VSCode and add site to it: `File > Add Folder to Workspace > BlogFood`

## New post
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

More: https://gohugo.io/getting-started/quick-start/#add-content


## Publish online
- set draft = false in post .md file (ex: `posts/my-second-post/index.md`)
- generate site (some HTML and CSS files will be generated in `public/` directory)
```sh
hugo
Start building sites … 
                   | EN   
-------------------+------
  Pages            |  16  
  Paginator pages  |   0  
  Non-page files   |   1  
  Static files     | 113  
  Processed images |   1  
  Aliases          |   4  
  Sitemaps         |   1  
  Cleaned          |   0  

Total in 54 ms
```
- commit all files and push to github repo
```sh
git add . 
git commit -m "my second post"
git push -u origin main
```
- New content will appear online shortly (progress can be monitored at https://github.com/danuts-thegreat/blogfood/actions)


