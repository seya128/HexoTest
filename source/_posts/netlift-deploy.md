---
title: netliftyにデプロイ
date: 2018-07-05 17:39:26
thumbnail: https://lh3.googleusercontent.com/mNOCTq5RxV8JaZONUminIjbThYc4ujE_Lb5x8fwiYJ3Mde4XLzqi-ho3fS6YTLIndsjPXjizQoNIxsrNDLA4Ym_bVwXDac8L8Vnn8EX5ya8gk754uccVR2-sr-IMywNOF2iYMnB7rAg
categories:
- コーディング
- Hexo
tags:
- Hexo
- デプロイ
- netlifty
---
<img src="https://lh3.googleusercontent.com/mNOCTq5RxV8JaZONUminIjbThYc4ujE_Lb5x8fwiYJ3Mde4XLzqi-ho3fS6YTLIndsjPXjizQoNIxsrNDLA4Ym_bVwXDac8L8Vnn8EX5ya8gk754uccVR2-sr-IMywNOF2iYMnB7rAg" width="100%" />

![](https://lh3.googleusercontent.com/mNOCTq5RxV8JaZONUminIjbThYc4ujE_Lb5x8fwiYJ3Mde4XLzqi-ho3fS6YTLIndsjPXjizQoNIxsrNDLA4Ym_bVwXDac8L8Vnn8EX5ya8gk754uccVR2-sr-IMywNOF2iYMnB7rAg=w1259-h944-no)
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
