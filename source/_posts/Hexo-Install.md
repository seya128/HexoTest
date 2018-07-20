---
title: Hexo インストール
date: 2018-07-05 15:38:34
thumbnail: https://pbs.twimg.com/profile_images/476729162707644418/mQZOTo9f_400x400.png
categories:
- CODING
- Hexo
tags:
- Hexo
- Install
---
すごく簡単。

node.jsとnpmはインストール済みの状態から始めます。
```
>node -v
v8.9.4

>npm -v
6.1.0
```

Winodwsで行いました。

## hexo-cliインストール
```
>npm install hexo-cli -g
C:\Program Files (x86)\Nodist\bin\hexo -> C:\Program Files (x86)\Nodist\bin\node_modules\hexo-cli\bin\hexo
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.4 (node_modules\hexo-cli\node_modules\fsevents):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@1.2.4: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"})

+ hexo-cli@1.1.0
added 103 packages in 35.504s
```
ワーニングは無視。

## ブログフォルダ作成

hexo init <ブログフォルダ名>
で、現在のフォルダの下に指定のフォルダが作成され、その中に色々なファイルが作成されます。

```
>hexo init hexo1st
INFO  Cloning hexo-starter to C:\Data\2018\Hexo\hexo1st
Cloning into 'C:\Data\2018\Hexo\hexo1st'...
remote: Counting objects: 65, done.
remote: Total 65 (delta 0), reused 0 (delta 0), pack-reused 65
Unpacking objects: 100% (65/65), done.
Checking connectivity... done.
Submodule 'themes/landscape' (https://github.com/hexojs/hexo-theme-landscape.git) registered for path 'themes/landscape'
Cloning into 'themes/landscape'...
remote: Counting objects: 824, done.
remote: Total 824 (delta 0), reused 0 (delta 0), pack-reused 823
Receiving objects: 100% (824/824), 2.54 MiB | 2.19 MiB/s, done.
Resolving deltas: 100% (435/435), done.
Checking connectivity... done.
Submodule path 'themes/landscape': checked out '73a23c51f8487cfcd7c6deec96ccc7543960d350'
?[43mWARN ?[49m Failed to install dependencies. Please run 'npm install' manually!
```

## ブログフォルダ内の初期化
このままでは、必要なnodeモジュールがインストールされていないので、ブログフォルダで以下のようなコマンドを実行します。
```
>cd hexo1st
>npm install
npm WARN deprecated titlecase@1.1.2: no longer maintained
npm WARN lifecycle The node binary used for scripts is C:\Program Files (x86)\Nodist\bin\node.exe but npm is using C:\Program Files (x86)\Nodist\v-x64\8.9.4\node.exe itself. Use the `--scripts-prepend-node-path` option to include the path for the node binary npm was executed with.

> nunjucks@3.1.3 postinstall c:\Data\2018\Hexo\hexo1st\node_modules\nunjucks
> node postinstall-build.js src

npm notice created a lockfile as package-lock.json. You should commit this file.
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.4 (node_modules\fsevents):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@1.2.4: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"})

added 400 packages in 78.504s
```

## プレビュー

```
>hexo s
INFO  Start processing
INFO  Hexo is running at http://localhost:4000/. Press Ctrl+C to stop.
```
http://localhost:4000/ をブラウザで確認できます。

## 新規記事作成
```
>hexo new "記事ファイル名"
```

## ブログ更新
```
>hexo g
```
