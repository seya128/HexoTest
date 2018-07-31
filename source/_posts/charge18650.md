---
title: リチウムイオン電池(18650)を充電してみた
thumbnail: https://i.gyazo.com/70236f51ffa45bbccd8935f836ec01f0.jpg
categories:
  - DIY
  - Battery
tags:
  - Battery
  - 18650
  - DIY
date: 2018-07-31 21:17:53
---
充電制御モジュールを使って、リチウムイオン電池(18650)の充電がうまくできたのでまとめました。

リチウムイオン電池は、過充電、過放電を行うと危険な電池ということで、過充電をしないように充電制御モジュールを使う必要があります。

## 使ったもの
- [マイクロUSB 5V 1A 18650リチウムバッテリー充電器モジュール](https://amzn.to/2OxIp15)
- [18650 充電池 3.7V 3000mAh](https://amzn.to/2vl8mYN)
- [3.7V18650用電池ボックス](https://amzn.to/2viFFeQ)

<iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//rcm-fe.amazon-adsystem.com/e/cm?lt1=_blank&bc1=000000&IS2=1&bg1=FFFFFF&fc1=000000&lc1=0000FF&t=seyaorg-22&o=9&p=8&l=as4&m=amazon&f=ifr&ref=as_ss_li_til&asins=B010FJTEFC&linkId=543983cd7ae5607748d4da809f1b153e"></iframe> <iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//rcm-fe.amazon-adsystem.com/e/cm?lt1=_blank&bc1=000000&IS2=1&bg1=FFFFFF&fc1=000000&lc1=0000FF&t=seyaorg-22&o=9&p=8&l=as4&m=amazon&f=ifr&ref=as_ss_li_til&asins=B074W4QHGT&linkId=266960eeb8352bcdda2ff52a615aa20c"></iframe> <iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//rcm-fe.amazon-adsystem.com/e/cm?lt1=_blank&bc1=000000&IS2=1&bg1=FFFFFF&fc1=000000&lc1=0000FF&t=seyaorg-22&o=9&p=8&l=as4&m=amazon&f=ifr&ref=as_ss_li_til&asins=B00SUXZ6GC&linkId=a063cf7878c13801f5f9c90105fbfe4a"></iframe>

### マイクロUSB 5V 1A 18650リチウムバッテリー充電器モジュール
TP4056、DW01Aと２つのICで、過充電、過放電からバッテリーを守る安全設計なモジュールです。
![](https://images-na.ssl-images-amazon.com/images/I/51CJ850qguL.jpg)
TP4056は、充電時の電流、電圧を制御します。
充電電圧を4.2Vまでに制御し、満充電になるにつれて充電電流を落として、100mA以下になると充電終了。

DW01Aは、電圧を監視し、4.3V以上になったり、2.4V以下になった場合に、制御が働きます。

### 18650リチウムイオン電池
![](https://images-na.ssl-images-amazon.com/images/I/61jh3fq4Z%2BL._SL1200_.jpg)
今回買ったものは充電器とセットで安かったものです。  
18650電池には、保護回路付きのものと、保護回路がついてないものがあります。  
プラス側が、凸になっているものは、保護回路がついていると思っていたのですが、凸になっていても保護回路がついていないものがあるようです。  
判別方法は、電池の長さを計るとわかります。  
18650は、直径18mm、長さが65mmなので、保護回路がついていると65mmより長くなるはずです。  
自分が買ったものを測ってみたところ、ほぼ66mmだったので保護回路がなかったもののようです。  

安全面から次は保護回路ありのものを購入しようと思います。

## 充電してみた

制御モジュールの、B+,B-に18650バッテリーを接続し、その間の電圧を計測しながら充電してみた。

購入状態からの充電なので、最初から4Vぐらいを示していた。 ![](https://i.gyazo.com/70236f51ffa45bbccd8935f836ec01f0.jpg)
写真をとり忘れたが、充電電流は900mAぐらいだった。  
このモジュールの充電電流は、max1Aなのでいい感じです。 

TP4056のICそのものは、結構熱くなっている。  
ずっとは触っていられないほど。

## 4.2Vを超えても充電が終了しない
しばらく充電していると、充電電圧が4.2Vを超えた。
![](https://i.gyazo.com/62f17781480dc12bd223673603a233ac.jpg)
電流は、470mA。  
![](https://i.gyazo.com/48435deddcb2dd7c2d71a69a981d37c6.jpg)
電流は下がってきているものの、電圧も上がってきている。  
ビビりながらも、電流が100mAを下回れば、充電完了になると信じて見守る。

### 110mAまで電流落ちた
470mAから１時間ぐらいだろうか、110mAまで落ちてきた。  
![](https://i.gyazo.com/78fcd48ce51c2ede28045ca5b0d892ff.jpg)
電圧は、4.25V。  
4.3Vになれば、DW01Aの保護回路が働くはずだが、まだ大丈夫。
![](https://i.gyazo.com/568ce9ca9da61cfed01644f721b2eacb.jpg)

### 充電完了
充電モジュールのLEDが赤から緑にかわり、充電終了！
![](https://i.gyazo.com/10514dd88a79cd5b3a9c1eb34be837f0.jpg)
充電電流も0Aと、USBからの電力供給は終了。
![](https://i.gyazo.com/bd45437c7eb07a40e93c7a8048b73996.jpg)

バッテリーの電圧は、4.1Vちょっとぐらい。
