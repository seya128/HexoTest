---
title: grblのデフォルト設定値をメモしておく
categories:
  - DIY
  - CNC
tags:
  - grbl
  - CNC
  - bCNC
date: 2018-12-08 13:43:29
thumbnail: https://i.gyazo.com/4f2f68df0f965450cd6ecf9a6011cb89.jpg
---
低価格のCNCを組み立てて、なんとか動作するようになったが、X軸の動きが反対。
そのような設定を変更するには、grblの設定を変更すると対応出来るらしい。

## grblの現在値

```
$$
$0=10 (step pulse, usec)
$1=25 (step idle delay, msec)
$2=0 (step port invert mask:00000000)
$3=0 (dir port invert mask:00000000)
$4=0 (step enable invert, bool)
$5=0 (limit pins invert, bool)
$6=0 (probe pin invert, bool)
$10=3 (status report mask:00000011)
$11=0.010 (junction deviation, mm)
$12=0.002 (arc tolerance, mm)
$13=0 (report inches, bool)
$20=0 (soft limits, bool)
$21=0 (hard limits, bool)
$22=0 (homing cycle, bool)
$23=0 (homing dir invert mask:00000000)
$24=25.000 (homing feed, mm/min)
$25=500.000 (homing seek, mm/min)
$26=250 (homing debounce, msec)
$27=1.000 (homing pull-off, mm)
$100=800.000 (x, step/mm)
$101=800.000 (y, step/mm)
$102=800.000 (z, step/mm)
$110=500.000 (x max rate, mm/min)
$111=500.000 (y max rate, mm/min)
$112=500.000 (z max rate, mm/min)
$120=300.000 (x accel, mm/sec^2)
$121=300.000 (y accel, mm/sec^2)
$122=300.000 (z accel, mm/sec^2)
$130=200.000 (x max travel, mm)
$131=200.000 (y max travel, mm)
$132=200.000 (z max travel, mm)
ok
```
## 現在値の見方

使ってるアプリは、bCNCというPythonのツールです。
Macでも動くのでこれを使いました。

### 接続

1. USBインターフェイスを選択
1. 「開く」ボタンで接続

![](https://i.gyazo.com/6181f8e4a0154c66cf23063efe5c4b0f.png)

### ターミナルで確認

1. 「Terminal」ボタンを押す
1. 「Settings」ボタンを押す

![](https://i.gyazo.com/f0418de1db140dabe09ee737a571d158.png)

これで、現在の設定がウィンドウに表示されるのですが、そのウィンドウに次々と現在の状態が表示されていって、すぐにウィンドウの外にスクロールして見えなくなってしまいます。

#### 対処方法

1. 適当な行をマウスで選択しておく
1. [Settings]ボタンで設定を表示
1. [Shift]+マウスで、設定表示後の行をクリック
1. 複数行が選択された状態になるので、コピー
1. テキストエディタにペーストして、いらない行を削除

ずっと現在のステータスが出続けるのを、どうにかできればいんだけどなー

## 参考
- [電子工作専科のぐうたラボ Grblの設定](http://denshikousakusenka.blog.fc2.com/blog-entry-92.html)

- [手作りCNCフライス〔Grbl設定編〕 \| 一生、いちエンジニア。](http://ichirowo.com/2016/09/cnc_grbl/)