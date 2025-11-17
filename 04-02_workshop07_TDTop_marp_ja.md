---
marp: true
paginate: true
---
<style>
:root {
  font-family: 'Noto Sans JP';    
  color: #444;
}
:root ol {
  list-style-type: decimal;
}
:root h1, h2, h3, h4, h5, h6{
  font-family: 'Noto Sans JP Black';
  color: #2277cc;
}
pre, code {
  font-family: 'Roboto mono', 'Noto Sans JP';
  line-height: 1.5;
}
</style>

# Workshop 07:<br>TOPの基本と画像処理

---

## 前回の復習

前回は「バナナを回転させる」という簡単なプログラムを作成しました。実際にパッチングしながら復習していきましょう。

![height:360](https://i.ytimg.com/vi/1gxN1-dUfyw/maxresdefault.jpg)

- [【Introduction to TouchDesigner】Let's rotate Banana in 10min ! #00](https://youtu.be/1gxN1-dUfyw?si=BTAGPEDhAIexO7zQ)

---

## 完成例

![height:480](https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-16-163741.png)

- [ダウンロード](https://github.com/tado/tdexamples/blob/main/01-01_rotateBanana01.toe)

---

## ここからさらに発展!

![height:360](https://i.ytimg.com/vi/lWGknmeueMA/maxresdefault.jpg)

- [【 TouchDesigner初級講座 】基本操作と基本のTOP編 #01](https://youtu.be/lWGknmeueMA?si=T3v4-pCUgCAS07jG)

---

### 完成イメージ

![height:480](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/04/image-7.png?resize=1536%2C1034&ssl=1)

- [ダウンロード](https://github.com/tado/tdexamples/blob/main/01-02_rotateBanana02.toe)

---   

## TOPによる画像処理

TOPを使用した画像処理やスイッチングなどの基本的な操作を学びます。

---

### 画像処理を行うためのTOP

TOPの入力を元に画像処理を行うオペレーターが多数用意されています

- Edge TOP: エッジ検出
- Blur TOP: ぼかし
- Bloom TOP: 輝いているような効果
- Level TOP: レベル補正
- emboss TOP: 凹凸のあるような効果

など。実際に試してみましょう。

---

### TOPを切り替える

いろいろな画像処理をした結果を、切り替えながら見ることができるように、TOPを切り替えるためのオペレーターを使用してみます。

- Switch TOP: 複数のTOPを切り替える

---

### フィードバック効果

- Feedback TOP: フィードバック効果を作成するためのTOP

少し接続が難しいですが、フィードバック効果を作成するためのTOPです。実際に作成しながら解説していきます。

### タイリング

- Tile TOP: タイリングを行うTOP

TOPをタイル状に並べることができるTOPです。実際に作成しながら解説していきます。

---

### TOPの基本を使用したプログラム例

![height:480](https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-16-164929.png)

- [ダウンロード](https://github.com/tado/tdexamples/blob/main/01-03_imageProcessing.toe)

---

### TOPの基本を使用したプログラム例 02

さらに激しく変化させてみました!

![height:400](https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-16-165130.png)

- [ダウンロード](https://github.com/tado/tdexamples/blob/main/01-04_imageProcessing02.toe)

---

## 本日の課題

---

### 課題: ノイズで遊ぼう!

---

簡単に二次元から四次元のノイズを生成することのできるNoise TOPを使用して、試行錯誤しながら自分なりの「作品」をつくってみる。プログラムの原型は以下からダウンロードしてください。

![height:400px](https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-17-052805-scaled.png)
- [ノイズの基本サンプル](https://github.com/tado/tdexamples/blob/main/02-01_noiseBasic.toe)

---

まだ操作の基本を習得した段階ですが、まずはいろいろ試行錯誤しながら操作の基本感覚を身に付けていきましょう。その上で以下のような工夫をしてみてください。

---

**参考資料**

- [パーリンノイズ (wikipedia)](https://ja.wikipedia.org/wiki/%E3%83%91%E3%83%BC%E3%83%AA%E3%83%B3%E3%83%8E%E3%82%A4%E3%82%BA)
- [The Book of Shaders by Patricio Gonzalez Vivo & Jen Lowe](https://thebookofshaders.com/11/)

---

#### 基本: 使用されているオペレータのパラメーターを変化させてみる

- [Noise TOP](https://docs.derivative.ca/index.php?title=Noise_TOP) (noise1)
  - ノイズの細かさ
  - ノイズの複雑さ
  - ノイズの種類
  - ...など
- [LFO CHOP](https://docs.derivative.ca/index.php?title=LFO_CHOP) (lfo1)
  - 変化速度
  - 変化する波形の種類
  - ...など

---

- [HSV Adjust TOP](https://docs.derivative.ca/index.php?title=HSV_Adjust_TOP) (hsvadj1)
  - 色相を変えてみる (hue)
  - 再度を変えてみる (saturation)
  - 明るさを変えてみる (brightness)
  - ...など

---  

#### 応用: オペレーターを追加してみる

- Noise TOPにNoise TOPを接続するとどうなるか?
- HSV Adjust TOPの前後に別のTOPを追加してみる
- LFO CHOPを追加して他のパラメータに参照させてみる
- ...など

---

### ノイズを使用した作品例 1

- ノイズ+ノイズ、Bloomエフェクトの追加

![height:420](https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-17-060944-scaled.jpg)
- [ダウンロード](https://github.com/tado/tdexamples/blob/main/02-02_noiseAdvanced01.toe)

---

### ノイズを使用した作品例 2

- 万華鏡のようなパターンを生成

![height:420](https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-17-055046-scaled.jpg)
- [ダウンロード](https://github.com/tado/tdexamples/blob/main/02-03_noiseAdvanced02.toe)

---

## 実習!

- ノイズを使用した作品を作成してみましょう!
- 講義最後の40分程度で作品の発表を行います

---

## アンケート

- [https://forms.gle/f7LSBuvns7p2TeXXA](https://forms.gle/f7LSBuvns7p2TeXXA)

![height:480](https://qr.quel.jp/tmp/87b643f543239276bb00924507648d657f9bdb17.png)

