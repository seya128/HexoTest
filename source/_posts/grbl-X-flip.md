---
title: grblのX軸の動作を反転させる
categories:
  - DIY
  - CNC
tags:
  - grbl
  - CNC
  - bCNC
date: 2018-12-09 13:43:29
thumbnail: https://i.gyazo.com/4f2f68df0f965450cd6ecf9a6011cb89.jpg
---
[前回](/2018/12/08/grbl-default-value/)、grblの現在の設定を確認できたので、いよいよ設定を変更します。

## X軸反転
```
$3=0 (dir port invert mask:00000000)
```
この値を変更すれば良さそうです。

設定する値は、各ビットがそれぞれの軸に対応するようです。

|Value	|Mask	|Invert X	|Invert Y	|Invert Z|
|-------|-------|-----------|-----------|--------|
|0	    |00000000	|N	|N	|N  |
|1	    |00000001	|Y	|N	|N  |
|2	    |00000010	|N	|Y	|N  |
|3	    |00000011	|Y	|Y	|N  |
|4	    |00000100	|N	|N	|Y  |
|5	    |00000101	|Y	|N	|Y  |
|6	    |00000110	|N	|Y	|Y  |
|7	    |00000111	|Y	|Y	|Y  |

X軸だけ反転するので、
```
$3=1
```
とします。

反転しました！！

この値は、電源を落としても保存されるようです。

## 参考
- [Configuring Grbl v0\.9 · grbl/grbl Wiki · GitHub](https://github.com/grbl/grbl/wiki/Configuring-Grbl-v0.9)
- [電子工作専科のぐうたラボ Grblの設定](http://denshikousakusenka.blog.fc2.com/blog-entry-92.html)

