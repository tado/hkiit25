## Workshop 04:<br>TidalCycles Practical Tutorai 1<br>Rhythm Creation

## 復習: シーケンス

### シーケンス

  * シーケンス: 反復進行(はんぷくしんこう sequence)
  * 同じ音のまとまりを何度も繰り返すこと
  * Strudelでは様々な方法でシーケンスを組み立てられる

### シーケンス基本

```haskell
-- TidalCycles
d1 $ sound "bd hc sd ho"
```
```javascript
// Strudel
$: s("bd hh sd oh")
```
* シーケンスの基本
* スペースで区切ることでシーケンス内で複数のサウンドを再生できる

### シーケンス基本

**主なドラムサウンド**

  * bd: バスドラム「ドスッ」
  * sd: スネアドラム「スタッ」
  * hc (hh): ハイハット「チッ」
  * ho (oh): オープンハイハット「チー」
  * rim: リムショット「カコッ」
  * lt: ロータム「ドコ」
  * mt: ミッドタム「トコ」
  * ht: ハイタム「ポコ」
  * cr: クラッシュシンバル「ガシャーン」
  * cp: クラップ「パン」

### 沢山の音を鳴らす

```haskell
-- TidalCycles
d1 $ sound "bd bd hc bd sd bd hc bd"
```
```
// Strudel
$: s("bd bd hh bd sd bd hh bd")
```

  * シーケンスが長い(たくさんの音がある)ほど速くなる
  * シーケンスの中身が1サイクルに押し込められるため

### テンポを変更する

```haskell
-- TidalCycles
d1 $ sound "bd bd hc bd sd bd hc bd" # cps(100/240)
``` 
```
// Strudel
$: s("bd bd hh bd rim bd hh bd").cpm(40)
```

* 1つの方法は cpm() を使用する方法
* cycle per minutes
* 1分あたり何サイクルするか、という単位
* その他にも方法があるがまた後述

### 休符

```haskell
-- TidalCycles
d1 $ sound "bd ~ hc ~ cp"
```
```
// Strudel
$: s("bd ~ hh ~ cp")
```

* \~は休符(音を出さないパート)をあらわす

### サブシーケンス

```haskell
-- TidalCycles
d1 $ sound "bd [hc hc] sd [hc ~ bd]"
```
```
// Strudel
$: s("bd [hh hh] sd [hh ~ bd]")
```

* []で囲うとサブシーケンスが作成される
* シーケンスの1要素の中をさらに分割するイメージ

### かけ算 - スピードアップ

```haskell
-- TidalCycles
d1 $ sound "bd hc*2 cp hc*3"
```
```
// Strudel
$: s("bd hh*2 cp hh*3")
```
* 「\* (かけ算)」記号はそのシーケンス内で分割してくりかえす
* かけ算の数だけスピードアップ

### シーケンスのスピードアップ

```haskell
-- TidalCycles
d1 $ sound "bd [hc ~ cp]*2"
```
```javascript
// Strudel
$: s("bd [hh ~ rim]*2")
```

* サブシーケンスのかけ算も可能
* []で囲まれたパートをスピードアップして繰り返す

### 超高速かけ算

```haskell
-- TidalCycles
d1 $ sound "bd ~ hc*16 ~ cp ~ hc*8"
```
```javascript
// Strudel
$: s("bd ~ hh*16 ~ rim ~ hh*8")
```
* かけ算の数を大きくすると分割が細かくなる
* どんどん速くしてくと、徐々に音程に聞こえてくる

### サブ・サブシーケンス

```haskell
-- TidalCycles
d1 $ sound "bd [cp [hc hc] cp] hc"
```
```javascript
// strudel
$: s("bd [ rim [hh hh] rim] hh")
```

* []を入れ子構造にすることで、サブシーケスのサブシーケンスをつくる

## 本日の内容: 変なリズムを作ってみよう!

### 変なリズムの作り方

* パラレルに演奏
  * ポリリズム
  * ポリミーター
* ユークリッドリズム

### パラレルに演奏

```haskell
-- TidalCycles
d1 $ sound "hc hc hc, cp cp"
```
```javascript
// Strudel
$: s("hh hh hh, cp cp")
```

  * コンマ(,)で区切って2つのシーケンスを記述する
  * パラレルに2つのシーケンスが演奏される

### パラレルに演奏2

```haskell
-- TidalCycles
d1 $ sound "hc ~ hc ~ hc, cp cp, ~ hc, bd"
```
```javascript
// Strudel
$: s("hh ~ hh ~ hh, cp*5, ~ ht, bd")
```

  * パラレルに演奏するシーケンスは、いくつでも増やせる
  * どんどんコンマ(,)で区切っていくだけ

### パラレルに演奏3

```haskell
-- TidalCycles
d1 $ sound "hc ~ hc ~ hc, bd [cr, cp*4]"
```

```javascript
// Strudel
$: s("hh ~ hh ~ hh, bd [cr, cp*4]")
```

  * サブシーケンスの中で、さらにパラレルに演奏することも可能

## ポリリズム (Polyrhythm) とポリミーター (Polymeter)

  * ポリリズム (Polyrhythm) とポリミーター (Polymeter) と違い
    * ポリリズム: 1拍目が揃っていてその他の拍がずれていく
    * ポリミーター: 全ての拍が揃っていて、1拍目がずれていく

<img src = "https://i0.wp.com/ethanhein.com/wp/wp-content/uploads/2024/04/3-to-4-polymeter-vs-3-to-4-polyrhythm.png?ssl=1" width = "640" />

### ポリリズム Polyrhythm

```haskell
-- TidalCycles
d1 $ sound "bd sd, hc hc hc"
```

```javascript
// Strudel
$: s("bd sd, hh hh hh")
```

* 拍子の異なるリズムをパラレルに演奏してみる
* 独特な捩れたリズムが生成される → ポリリズム (polyrhythm)
* いろいろな拍子の組み合わせを試してみる\!

```haskell
-- TidalCycles
d1 $ sound "bd cr, hc*4, ~ cp cp ~ cp*2, ~ sd sd"
```

```javascript
// Strudel
$: s("bd cr, hh*4, ~ cp cp ~ cp*2, ~ sd sd")
```

* いろいろなポリリズムのパターンを演奏してみよう\!

### ポリミーター Polymeter

```haskell
-- TidalCycles
d1 $ sound "{bd sd, cp hc ho}"
```
```javascript
// Strudel
$: s("{bd sd, rim hh oh}")
```

* こんどは、パラレルに記述したパターンの両端を{}で囲んでみる
    * どう変化するか?
* 拍子は共通で、1拍目がずれていく → ポリミーター polymeter
* こちらもいろいろ試してみる\!

## ユークリッドリズム (Euclidean Rhythm)

### ユークリッドリズム Euclidean Rhythmとは？

* ユークリッドの互除法 (Euclidean Argorhythm) を元に生成されるリズムパターン
* 左: (3, 8), 右: (5, 8)
<img src="https://i0.wp.com/yoppa.org/wp-content/uploads/2024/10/a-The-Euclidean-rhythm-E3-8-is-the-Cuban-tresillo-b-The-Euclidean-rhythm-E5-8.png?w=850&ssl=1" width="640" />

* 世界中の様々な民族音楽のリズムパターンに見られる
* 例: キューバン・トレスィージョ (Cuban Tresillo), ブラジルのサンバ (Samba), 西アフリカのアガデス (Agadez) など

### ユークリッドリズムのつくり方

  * (3,8)の場合
      * [11100000]
      * [10] [10] [10] [00]
      * [100][100][10]
      * [10010010]
  * (5,8)の場合
      * [11111000]
      * [10][10][10][11]
      * [101] [101] [10]
      * [10110110]

```haskell
-- TidalCycles
d1 $ sound "bd(3, 8), hc(9, 16)"
```
```javascript
// Strudel
$: s("bd(3, 8), hh(9, 16)")
```

* ユークリッドリズムの例
* 複雑なリズムパターンがいろいろ作成可能
* 試してみよう\!

```haskell
-- TidalCycles
d1 $ sound "bd(3, 7), hc(9, 14, 5), cp(5, 7, 2)"
```
```javascript
// Strudel
$: s("bd(3, 7), hh(9, 14, 5), cp(5, 7, 2)")
```

* 分母を奇数にすると、変拍子(奇数拍子)のリズムが生成できる\!
* 世界の様々な民族音楽のリズム構造を模倣可能

## エフェクト

```haskell
-- TidalCycles
d1 
  $ sound "bd sd [~ bd] hc"
  # delay 0.8
  # delaytime (5/8)
  # lock 1
```
```javascript
// Strudel
$: s("bd sd [~ bd] hh")
   .bank("tr909")
   .delay(0.8).delaytime(5/8)
```

  * TidalCycles / Strudelには様々なエフェクトが容易されている
  * ディレイ、リバーブ、フランジャーなど
  * 試しにリズムにディレイをかけてみる
  * ディレイタイムを工夫すると、グルーブが生まれてくる\!

```haskell
-- TidalCycles
d1 
  $ sound "bd cp [~ bd] hc*2, bd:2(3,8), hc*8, cp(7,8)"
  # delay 0.8 # delaytime (9/8) # delayfeedback 0.5
  # lock 1
  # lpf (range 400 8000 $ slow 16 $ sine)
  # resonance 0.2
  # room 0.5 # size 0.5
```
```javascript
// Strudel
$: s("bd cp [~ bd] hh*2, bd:2(3,8), hh*8, cp(7,8)")
   .bank("tr909")
   .delay(0.8).delaytime(9/8).delayfeedback(0.5)
   .lpf(sine.segment(128).range(400,8000).slow(16)).resonance(10)
   .room(0.5).size(1.5)
   .punchcard().color("pink")
```

  * さらに様々なエフェクトを加えてみる\!
  * ディレイ+ リバーブ+ローパスフィルター

## 実習: 変なリズムを作ってみる\!

### 本日の実習\!

  * Strudelを使用して「変な」リズムを作ってみよう\!
  * 変拍子、奇数拍子、ポリリズム、ポリミーターなど
  * 普通ではなく、かつめちゃくちゃでもない微妙な加減を工夫してみましょう\!
  * 参考
  * 変なリズムの曲をSpotifyでプレイリストにまとめてみました\!
  * [https://open.spotify.com/playlist/6J9H9ErKXep2xjPqvi09OB](https://open.spotify.com/playlist/6J9H9ErKXep2xjPqvi09OB)