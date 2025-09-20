---
date: '2025-09-20T10:09:05+08:00'
draft: false
title: '我如何建立這個網站的'
---

紀錄我如何完成這個網站的(還在整理中)

首先安裝 Hugo，接著創建一個資料夾，在資料夾裡開起終端機。  

## 使用 Hugo 建立靜態網頁
創建 Hugo 專案（名稱 jerryyy，--format yaml 是因為安裝 PaperMod 需要的）
```
hugo new site jerryyy --format yaml
```

進入 jerryyy 資料夾 
```
cd jerryyy/
```

初始化 git 並且下載想要的 theme，我用的 theme 是 PaperMod，[官方文檔](https://adityatelange.github.io/hugo-PaperMod/)在這裡。
```
git init

git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```

將 "theme: PaperMod" 加入 hugo.yaml，創建 "config.yml" 在 theme/PaperMod 資料夾裡，並且在 config.yml 中寫入以下容（這來自[官方文檔](https://adityatelange.github.io/hugo-PaperMod/posts/papermod/papermod-installation/)）

```
baseURL: "https://thisisjerry7.github.io/"
title: ExampleSite
paginate: 5
theme: PaperMod

enableRobotsTXT: true
buildDrafts: false
buildFuture: false
buildExpired: false

googleAnalytics: UA-123-45

minify:
  disableXML: true
  minifyOutput: true

params:
  env: production # to enable google analytics, opengraph, twitter-cards and schema.
  title: ExampleSite
  description: "ExampleSite description"
  keywords: [Blog, Portfolio, PaperMod]
  author: Me
  # author: ["Me", "You"] # multiple authors
  images: ["<link or path of image for opengraph, twitter-cards>"]
  DateFormat: "January 2, 2006"
  defaultTheme: auto # dark, light
  disableThemeToggle: false

  ShowReadingTime: true
  ShowShareButtons: true
  ShowPostNavLinks: true
  ShowBreadCrumbs: true
  ShowCodeCopyButtons: false
  ShowWordCount: true
  ShowRssButtonInSectionTermList: true
  UseHugoToc: true
  disableSpecial1stPost: false
  disableScrollToTop: false
  comments: false
  hidemeta: false
  hideSummary: false
  showtoc: false
  tocopen: false

  assets:
    # disableHLJS: true # to disable highlight.js
    # disableFingerprinting: true
    favicon: "<link / abs url>"
    favicon16x16: "<link / abs url>"
    favicon32x32: "<link / abs url>"
    apple_touch_icon: "<link / abs url>"
    safari_pinned_tab: "<link / abs url>"

  label:
    text: "Home"
    icon: /apple-touch-icon.png
    iconHeight: 35

  # profile-mode
  profileMode:
    enabled: false # needs to be explicitly set
    title: ExampleSite
    subtitle: "This is subtitle"
    imageUrl: "<img location>"
    imageWidth: 120
    imageHeight: 120
    imageTitle: my image
    buttons:
      - name: Posts
        url: posts
      - name: Tags
        url: tags

  # home-info mode
  homeInfoParams:
    Title: "Hi there \U0001F44B"
    Content: Welcome to my blog

  socialIcons:
    - name: x
      url: "https://x.com/"
    - name: stackoverflow
      url: "https://stackoverflow.com"
    - name: github
      url: "https://github.com/"

  analytics:
    google:
      SiteVerificationTag: "XYZabc"
    bing:
      SiteVerificationTag: "XYZabc"
    yandex:
      SiteVerificationTag: "XYZabc"

  cover:
    hidden: true # hide everywhere but not in structured data
    hiddenInList: true # hide on list pages and home
    hiddenInSingle: true # hide on single page

  editPost:
    URL: "https://github.com/<path_to_repo>/content"
    Text: "Suggest Changes" # edit text
    appendFilePath: true # to append file path to Edit link

  # for search
  # https://fusejs.io/api/options.html
  fuseOpts:
    isCaseSensitive: false
    shouldSort: true
    location: 0
    distance: 1000
    threshold: 0.4
    minMatchCharLength: 0
    limit: 10 # refer: https://www.fusejs.io/api/methods.html#search
    keys: ["title", "permalink", "summary", "content"]
menu:
  main:
    - identifier: categories
      name: categories
      url: /categories/
      weight: 10
    - identifier: tags
      name: tags
      url: /tags/
      weight: 20
    - identifier: example
      name: example.org
      url: https://example.org
      weight: 30
# Read: https://github.com/adityatelange/hugo-PaperMod/wiki/FAQs#using-hugos-syntax-highlighter-chroma
pygmentsUseClasses: true
markup:
  highlight:
    noClasses: false
    # anchorLineNos: true
    # codeFences: true
    # guessSyntax: true
    # lineNos: true
    # style: monokai
```

以下是我修改過的
```
baseURL: "https://thisisjerry7.github.io/"
title: ExampleSite
paginate: 5
theme: PaperMod

enableRobotsTXT: true
buildDrafts: false
buildFuture: false
buildExpired: false

googleAnalytics: UA-123-45

minify:
  disableXML: true
  minifyOutput: true

params:
  env: production # to enable google analytics, opengraph, twitter-cards and schema.
  title: ExampleSite
  description: "ExampleSite description"
  keywords: [Blog, Portfolio, PaperMod]
  author: Me
  # author: ["Me", "You"] # multiple authors
  images: ["<link or path of image for opengraph, twitter-cards>"]
  DateFormat: "January 2, 2006"
  defaultTheme: auto # dark, light
  disableThemeToggle: false

  ShowReadingTime: true
  ShowShareButtons: true
  ShowPostNavLinks: true
  ShowBreadCrumbs: true
  ShowCodeCopyButtons: false
  ShowWordCount: true
  ShowRssButtonInSectionTermList: true
  UseHugoToc: true
  disableSpecial1stPost: false
  disableScrollToTop: false
  comments: false
  hidemeta: false
  hideSummary: false
  showtoc: false
  tocopen: false

  assets:
    # disableHLJS: true # to disable highlight.js
    # disableFingerprinting: true
    favicon: "<link / abs url>"
    favicon16x16: "<link / abs url>"
    favicon32x32: "<link / abs url>"
    apple_touch_icon: "<link / abs url>"
    safari_pinned_tab: "<link / abs url>"

  label:
    text: "Home"
    icon: /apple-touch-icon.png
    iconHeight: 35

  # profile-mode
  profileMode:
    enabled: false # needs to be explicitly set
    title: ExampleSite
    subtitle: "This is subtitle"
    imageUrl: "<img location>"
    imageWidth: 120
    imageHeight: 120
    imageTitle: my image
    buttons:
      - name: Posts
        url: posts
      - name: Tags
        url: tags

  # home-info mode
  homeInfoParams:
    Title: "Hi there 歡迎～ \U0001F44B"
    Content: Welcome to my blog

#  socialIcons:
#    - name: x
#      url: "https://x.com/"
#    - name: stackoverflow
#      url: "https://stackoverflow.com"
#    - name: github
#      url: "https://github.com/"

  analytics:
    google:
      SiteVerificationTag: "XYZabc"
    bing:
      SiteVerificationTag: "XYZabc"
    yandex:
      SiteVerificationTag: "XYZabc"

  cover:
    hidden: true # hide everywhere but not in structured data
    hiddenInList: true # hide on list pages and home
    hiddenInSingle: true # hide on single page

#  editPost:
#    URL: "https://github.com/<path_to_repo>/content"
#    Text: "Suggest Changes" # edit text
#    appendFilePath: true # to append file path to Edit link

  # for search
  # https://fusejs.io/api/options.html
  fuseOpts:
    isCaseSensitive: false
    shouldSort: true
    location: 0
    distance: 1000
    threshold: 0.4
    minMatchCharLength: 0
    limit: 10 # refer: https://www.fusejs.io/api/methods.html#search
    keys: ["title", "permalink", "summary", "content"]
menu:
  main:
    - identifier: use
      name: 愛用
      url: /use/
      weight: 20
    - identifier: posts
      name: 貼文
      url: /posts/
      weight: 30
    - identifier: categories
      name: categories
      url: /categories/
      weight: 10
#    - identifier: tags
#      name: tags
#      url: /tags/
#      weight: 20
#    - identifier: example
#      name: example.org
#      url: https://example.org
#      weight: 30
# Read: https://github.com/adityatelange/hugo-PaperMod/wiki/FAQs#using-hugos-syntax-highlighter-chroma
pygmentsUseClasses: true
markup:
  highlight:
    noClasses: false
    # anchorLineNos: true
    # codeFences: true
    # guessSyntax: true
    # lineNos: true
    # style: monokai
```

啟動 Hugo，-D 的意思是草稿也會顯示出來
```
hugo server -D
```

用 Hugo 產生靜態網頁，會放在 public 資料夾裡。
```
hugo
```


## 將網站透過 git 發布到 Github Pages

首先在 Github 新建一個 repository，Repository name 打上{使用者名稱}.github.io，visibility 選擇 Public or Private 都可以，我選擇 Private，沒有設定新增任何東西，按下 Create repository。
因為我是在 ubuntu 上使用的，所以我用 SSH 跟 Github 連線，到 Github 裡的 Settings 裡的 SSH and GPG keys，參考[這篇文章](https://ithelp.ithome.com.tw/articles/10205988)
接著打開電腦上的終端機，輸入
```
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

如果成功會出現
```
Generating public/private rsa key pair.
Enter a file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter]
Enter passphrase (empty for no passphrase): [Type a passphrase]
Enter same passphrase again: [Type passphrase again]
```

Generating public/private rsa key pair.
此行的意思就是會根據提供的 email 創建一個新的 SSH 金鑰。

Enter a file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter]
這一行是確認儲存的位置，可以直接按下 Enter 就好。

Enter passphrase (empty for no passphrase): [Type a passphrase] Enter same passphrase again: [Type passphrase again]
這兩行是要輸入密碼與確認密碼，如果不輸入就空白即可。

到這邊就成功了！

在 .ssh/ 資料夾下會分別有 id_rsa、id_rsa.pub 這兩個檔案，也就分別代表私鑰及公鑰，這一個步驟就是將 id_rsa.pub 也就是公鑰上傳到 Github 上。
```
cat ~/.ssh/id_rsa.pub
```

複製公鑰到 Github 上

然後設定帳號
```
git config --global user.name "你的名稱"
git config --global user.email "你的電子郵件"
```

到專案點 Code頁面，依照指示新增連線，以下是頁面大致的樣子

…or create a new repository on the command line
```
echo "# test" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:{username}/test.git
git push -u origin main
```
…or push an existing repository from the command line
```
git remote add origin git@github.com:{username}/test.git
git branch -M main
git push -u origin main
```


用 git 將主程式儲存在 master
```
git add .
git commit -m "test1"
git remote add origin git@github.com:{username}/{username}.github.io.git
git push origin master
```

將 Hugo 產生的靜態網頁儲存在 gh-pages 分支
```
cd public
git init
git add .
git commit -m "test2-web"
git remote add origin git@github.com:{username}/{username}.github.io.git
git push -u origin master:gh-pages
```

在 Github 的 Settings 裡的 Pages，把 Branch 改成 gh-pages，打開 https://{用戶名}.github.io/ 就成功了。
這個專案的網址：
https://thisisjerry7.github.io/


## Hugo 指令
參考[官方文檔](https://hugo.opendocs.io/getting-started/quick-start/)

建立文章
```
hugo new posts/123.md   #123換成文章的名字
```



參考資料：  
[使用 Hugo 在 Github Pages 建立靜態網站](https://hackmd.io/@udzQ2BohS5C0Xc66dtaYIA/S1wSWRbrO)  
[Hugo + Github + Netlify免費架設靜態網站教學](https://ivonblog.com/posts/build-a-website-with-hugo/)  
[Hugo themes](https://themes.gohugo.io/)  
[PaperMod’s Demo](https://adityatelange.github.io/hugo-PaperMod/)  
[設定 Github SSH 金鑰 feat. Github SSH、HTTPS 的差異](https://ithelp.ithome.com.tw/articles/10205988)  
[Git 教學和 GitHub 設定指引](https://hackmd.io/@sysprog/git-with-github)  



