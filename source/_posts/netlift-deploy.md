---
title: netliftyにデプロイ
date: 2018-07-05 17:39:26
thumbnail: https://i.gyazo.com/25fdd93ed497fb5f4fb10724493cec5b.png
categories:
- CODING
- Hexo
tags:
- Hexo
- Deploy
- netlifty
---
![](https://i.gyazo.com/25fdd93ed497fb5f4fb10724493cec5b.png)

## netliftyでブログを公開

https://www.netlify.com/

ここでサインアップして、
・New site from Git
・GitHubと、リポジトリを選択する
これだけで、ブログがデプロイ、公開される。

最初は、デプロイエラーが出た。

公開URLが設定されていなかったのが原因っぽい。

_config.ymlを変更
```
url: https://nostalgic-benz-138008.netlify.com
```
githubにプッシュすると、勝手にデプロイして公開された。

https://nostalgic-benz-138008.netlify.com/

簡単すぎる！
