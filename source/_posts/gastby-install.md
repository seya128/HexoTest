---
title: Gastbyインストール
categories:
  - CODING
  - Gatsby
tags:
  - Gatsby
  - pyenv
date: 2019-01-23 22:17:29
thumbnail: https://i.gyazo.com/3b347cc14ee5af4a394b9a3072e97fb8.png
---

# Gatsbyとは

Reactを使った静的ページジェネレーター

静的ページジェネレーターなのに、いろいろモダンなことができるらしい。

以下のサイトにしたがって、インストールからサンプルページの立ち上げまで行ってみた。

https://github.com/gatsbyjs/gatsby

５分でサンプルサイトが立ち上がるはずが、１時間かかった。

# ハマりポイント

gatsby-cliは、python3系には対応していない。
python 2.7系を使おう！

## python 3を、2.7系にする方法

```
pyenv install 2.7.14
pyenv local 2.7.14
```
これで、このフォルダ配下では2.7.14になる。

installで以下のようなエラーが出た。

```
ERROR: The Python zlib extension was not compiled. Missing the zlib?
```
この場合、次のようにインストール
```
CFLAGS="-I$(xcrun --show-sdk-path)/usr/include" pyenv install -v 2.7.
```
バージョン確認
```
python -V
```




## Gatsbyインストール

```
sudo npm install -g gatsby-cli
gatsby new my-blazing-fast-site
cd my-blazing-fast-site/
gatsby develop
```

http://localhost:8000/
で、サイトが確認できる。

ちなみに、python3のままやると、
```
error Unable to find plugin "gatsby-transformer-sharp". Perhaps you need to install its package?
```
こんなエラーが出る。


次は、これを立ち上げよう
https://github.com/ryanwiemer/gatsby-starter-gcn

