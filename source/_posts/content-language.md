---
title: 「このページを翻訳しますか？」対策
date: 2018-07-10 21:50:07
thumbnail: https://pbs.twimg.com/profile_images/476729162707644418/mQZOTo9f_400x400.png
categories:
- コーディング
- Hexo
tags:
- Hexo
- テーマ
- HTML
---
![](https://pbs.twimg.com/profile_images/476729162707644418/mQZOTo9f_400x400.png)
Hexoで生成されたページをChromeで表示すると「このページを翻訳しますか？」と毎回出てうっとおしかったので対策をした。

## 対策

`<head></head>`内に、以下一行を入れれば解決するということです。
```html
<meta http-equiv="content-language" content="ja">
```

参考 : [中国語（繁体字）のページです。日本語に翻訳しますか？ \- アースリバー開発記](http://ejoun.hatenablog.com/entry/2017/09/04/235605)

## Hexoテーマへの反映

Hexoでは、_config.ymlに、languageを指定しているので、その値を使ってcontentの値を設定します。

huemanテーマでは、
themes/hueman/layout/common/head.ejs
を、書き換えます。

```html
<head>
    <meta charset="utf-8" />
    <meta http-equiv="content-language" content="<%= config.language %>">
    <%- partial('pwa/index') %>
```
こんな感じです。

`<%= config.language %>`
で、_config.ymlのlanguageの設定を持ってくるということですね。
