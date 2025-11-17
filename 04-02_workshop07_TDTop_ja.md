# Workshop 07: TOPの基本と画像処理

## 前回の復習

前回は「バナナを回転させる」という簡単なプログラムを作成しました。Movie File In TOP でバナナ画像を読み込み、Transform TOP で回転のアニメーションを設定し、Circle TOP で作成した円と Over TOP で合成しましたね。実際にパッチング（オペレーターを繋いでいく作業）をしながら、基本的な操作方法を復習していきましょう。

<img src="https://i.ytimg.com/vi/1gxN1-dUfyw/maxresdefault.jpg" width="640" />

- [【Introduction to TouchDesigner】Let's rotate Banana in 10min ! #00](https://youtu.be/1gxN1-dUfyw?si=BTAGPEDhAIexO7zQ)
  この動画を見ながら、前回の操作を思い出してみましょう。

## 完成例

前回の内容を発展させた完成例です。基本的な回転に加えて、背景なども追加されています。

<img src="https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-16-163741.png" width="640" />

- [ダウンロード](https://github.com/tado/tdexamples/blob/main/01-01_rotateBanana01.toe)
  完成例のファイル（.toe）をダウンロードして、TouchDesignerで開いてみてください。どのように作られているか、中身を確認できます。

## ここからさらに発展!

前回の復習で作成した「回転するバナナ」をベースに、さらにTOPを使った画像処理を加えて表現を豊かにしていきます。以下の動画で解説されている内容を参考に、様々なTOPオペレーターを使ってみましょう。

<img src="https://i.ytimg.com/vi/lWGknmeueMA/maxresdefault.jpg" width="640" />

- [【 TouchDesigner初級講座 】基本操作と基本のTOP編 #01](https://youtu.be/lWGknmeueMA?si=T3v4-pCUgCAS07jG)
  この動画では、基本的なTOPオペレーターの種類や接続方法、パラメータの調整方法などが解説されています。

### 完成イメージ

発展させた最終的な完成イメージです。様々なエフェクトが追加されているのが分かります。

<img src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/04/image-7.png?resize=1536%2C1034&ssl=1" width="640" />

- [ダウンロード](https://github.com/tado/tdexamples/blob/main/01-02_rotateBanana02.toe)
  こちらもダウンロードして、どのようなオペレーターがどのように接続されているか確認してみましょう。



## TOPによる画像処理

ここからは、今回の講義のメインテーマであるTOPを使った画像処理について詳しく学んでいきます。TOPはTexture Operatorsの略で、TouchDesignerで画像や映像を扱ったり、加工したりするためのオペレーター群です。

### 画像処理を行うためのTOP

TouchDesignerには、入力された画像に対して様々な効果を加えるためのTOPが豊富に用意されています。いくつか代表的なものを紹介します。

- Edge TOP: 画像の輪郭（エッジ）を検出します。イラストのような表現や、特定の形状を抽出したい場合に便利です。
- Blur TOP: 画像にぼかし効果を加えます。ぼかしの強さや方向などを調整できます。
- Bloom TOP: 画像の明るい部分を滲ませ、光り輝いているような効果（ブルーム効果）を作り出します。幻想的な表現に適しています。
- Level TOP: 画像の明るさ、コントラスト、ガンマなどを調整します。色調補正の基本的なオペレーターです。
- Emboss TOP: 画像に凹凸があるような、浮き彫り風の効果を加えます。

これらのTOPは、オペレーターパレット（Tabキーで表示）のTOPタブから作成できます。入力（左側の接続点）に画像データを持つTOPを接続し、パラメータウィンドウで効果の具合を調整します。実際にいくつか試して、どのような効果が得られるか確認してみましょう。

### TOPを切り替える

複数の画像や、異なる画像処理を施した結果を、状況に応じて切り替えたい場合があります。そのような時に使うのがSwitch TOPです。

- Switch TOP: 複数のTOP入力を受け取り、指定した一つの入力だけを出力します。パラメータの「Index」を変化させることで、どの入力を選択するかを切り替えることができます。例えば、異なるエフェクトをかけた結果を比較したり、インタラクションに応じて表示する映像を切り替えたりする際に使用します。

### フィードバック効果

映像表現でよく使われる「フィードバック」効果を作成するための専用TOPもあります。

- Feedback TOP: 前のフレーム（ほんの少し前の時間）の出力結果を、現在のフレームの処理に利用することで、残像や映像が無限に続くような効果を作り出します。
   接続のポイント: Feedback TOPの接続は少し特殊です。通常、処理ループの最後にFeedback TOPを配置し、そのFeedback TOPをループの最初（フィードバックさせたい入力）にドラッグ＆ドロップして参照させます。ループ内にはLevel TOPなどを入れてフィードバックの強さ（透明度など）を調整したり、Add TOPやOver TOPで元の画像と合成したりすることが一般的です。
   実際に作成しながら、この少し複雑な接続方法と、それによって生まれるユニークな表現を体験してみましょう。

### タイリング

画像をタイル状に並べてパターンを作成したい場合にはTile TOPを使用します。

- Tile TOP: 入力された画像をタイル状に敷き詰めます。並べ方（繰り返し、反転、回転など）や、タイルの数などをパラメータで細かく設定します。万華鏡のような表現や、テクスチャパターンを作成するのに便利です。

### TOPの基本を使用したプログラム例

ここまで紹介したTOPオペレーター（Edge, Blur, Level, Switch, Feedback, Tileなど）を組み合わせて作成したサンプルプログラムです。

<img src="https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-16-164929.png" width="640" />

- [ダウンロード](https://github.com/tado/tdexamples/blob/main/01-03_imageProcessing.toe)
  ダウンロードして、各オペレーターがどのように連携して最終的な映像を作り出しているかを確認してください。

### TOPの基本を使用したプログラム例 02

さらにパラメータを調整したり、別のTOPを追加したりして、より複雑でダイナミックな変化を持つようにした例です。

<img src="https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-16-165130.png" width="640" />

- [ダウンロード](https://github.com/tado/tdexamples/blob/main/01-04_imageProcessing02.toe)
  少しの変更で大きく表現が変わることを体験してみてください。



## 本日の課題

### 課題: ノイズで遊ぼう!

今回の課題では、Noise TOP を使って自由に表現を試みます。Noise TOP は、プログラムによって様々な種類のノイズ（ランダムで有機的なパターン）を生成することができる非常に強力なオペレーターです。パラメータを調整するだけで、雲、水面、炎、地形のような多種多様なテクスチャやアニメーションを作り出すことができます。

まずは以下の基本的なサンプルプログラムをダウンロードし、これを改造しながら自分だけの「ノイズ作品」を制作してみてください。

<img src="https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-17-052805-scaled.png" width="640" />
- [ノイズの基本サンプル](https://github.com/tado/tdexamples/blob/main/02-01_noiseBasic.toe)

TouchDesignerの操作に慣れるためには、とにかくいろいろ試してみることが重要です。難しく考えず、まずはパラメータを触ってみて、変化を観察することから始めましょう。その上で、以下のような点を意識して試行錯誤してみてください。

参考資料

これらの資料は、ノイズ、特にNoise TOPで使われているパーリンノイズというアルゴリズムについて理解を深めるのに役立ちます。

- [パーリンノイズ (wikipedia)](https://ja.wikipedia.org/wiki/%E3%83%91%E3%83%BC%E3%83%AA%E3%83%B3%E3%83%8E%E3%82%A4%E3%83%B3%E3%83%88)
- [The Book of Shaders by Patricio Gonzalez Vivo & Jen Lowe](https://thebookofshaders.com/11/) （特にChapter 11: Noise のセクションが参考になります）

#### 基本: 使用されているオペレータのパラメーターを変化させてみる

サンプルプログラムで使われている主要なオペレーターのパラメータをいろいろ変更してみましょう。

- [Noise TOP](https://docs.derivative.ca/index.php?title=Noise_TOP) (noise1): このネットワークの中心となるオペレーターです。
  - Period（周期）: ノイズの細かさ、スケール感を調整します。値が小さいほど細かいノイズになります。
  - Harmonics（高調波）: ノイズの複雑さを調整します。値を大きくすると、より詳細で複雑なパターンになります。
  - Type（種類）: 生成するノイズのアルゴリズムを選択します。Perlin, Simplex, Randomなど、種類によって見た目が大きく変わります。色々試してみましょう。
  - TransformタブのTranslate/Rotate/Scale: ノイズを時間経過で動かしたり（Translate Zに absTime.seconds などのエクスプレッションを入れる）、回転させたり、拡大縮小したりできます。
  - ...など、他にもたくさんのパラメータがあります。気になるものを触ってみましょう。

- [LFO CHOP](https://docs.derivative.ca/index.php?title=LFO_CHOP) (lfo1): 時間と共に周期的な値（波形）を生成するCHOP (Channel Operator) です。この値を使って他のオペレーターのパラメータを動かします。
  - Frequency（周波数）: 値が変化する速度を調整します。大きいほど速く変化します。
  - Type（波形タイプ）: Sine（サイン波）、Triangle（三角波）、Square（矩形波）など、値の変化パターンを選択します。
  - Amplitude（振幅）: 値が変化する範囲（大きさ）を調整します。
  - ...など。このLFO CHOPの出力をNoise TOPのパラメータ（例えば Amplitude）にエクスポート（ドラッグ＆ドロップ）して、ノイズの明るさを時間で変化させる、といった使い方ができます。

- [HSV Adjust TOP](https://docs.derivative.ca/index.php?title=HSV_Adjust_TOP) (hsvadj1): 色相（Hue）、彩度（Saturation）、明度（Value/Brightness）を調整して、画像の色味を変更するTOPです。
  - Hue Offset: 全体の色相をシフトさせます。値を変化させると色が循環するように変わります。
  - Saturation Multiplier: 彩度を調整します。0にするとグレースケールになります。
  - Value Multiplier: 明るさを調整します。
  - ...など。Noise TOPで生成したモノクロのノイズに色を付けたり、色を時間変化させたりするのに使えます。

#### 応用: オペレーターを追加してみる

基本操作に慣れてきたら、新しいオペレーターを追加して、さらに複雑な表現に挑戦してみましょう。

- Noise TOPにNoise TOPを接続する: Noise TOPの出力を別のNoise TOPの第二入力 (Noise Coordinate Map) に接続すると、一方のノイズで他方のノイズパターンを歪ませるような、非常に面白い効果が得られます。
- HSV Adjust TOPの前後に別のTOPを追加する: 例えば、Noise TOPとHSV Adjust TOPの間にBlur TOPを入れてノイズをぼかしたり、HSV Adjust TOPの後にBloom TOPを追加して光らせたり、Edge TOPで輪郭抽出してから色付けするなど、エフェクトを重ねてみましょう。
- LFO CHOPを追加して他のパラメータに参照させてみる: 新しいLFO CHOPを作成し、その値をNoise TOPの回転パラメータやHSV Adjust TOPの色相パラメータなどにエクスポートして、より複雑なアニメーションを作成してみましょう。
- ...など、自由な発想でオペレーターを繋ぎ変えてみてください。思わぬ発見があるかもしれません。

### ノイズを使用した作品例 1

- 内容: Noise TOPを二つ重ね（一つはパターン生成、もう一つは歪み用）、さらにBloom TOPで発光効果を追加した例です。
<img src="https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-17-060944-scaled.jpg" width="640" />

- [ダウンロード](https://github.com/tado/tdexamples/blob/main/02-02_noiseAdvanced01.toe)

### ノイズを使用した作品例 2

- 内容: Noise TOPにTile TOPを組み合わせて、万華鏡のような繰り返しパターンを生成した例です。色の変化も加えられています。
<img src="https://yoppa.org/wp-content/uploads/2025/04/Screenshot-2025-04-17-055046-scaled.jpg" width="640" />

- [ダウンロード](https://github.com/tado/tdexamples/blob/main/02-03_noiseAdvanced02.toe)



## 実習!

それでは、実際にNoise TOPを使って、自分だけのオリジナル作品を制作してみましょう！
まずは基本サンプルを改造することから始め、慣れてきたら自由にオペレーターを追加・接続してみてください。

- 目標: Noise TOPを中心に、学んだ各種TOP（Blur, Level, Bloom, Feedback, Tile, HSV Adjustなど）やCHOP（LFOなど）を組み合わせて、面白い、あるいは美しいと感じる映像表現を試みること。
- 時間: これから約XX分間（時間は先生が指定）を制作時間とします。
- 発表: 講義の最後の40分程度で、皆さんが作成した作品を一人ずつ発表してもらいます。完成していなくても構いませんので、どのような試行錯誤をしたか、どこが面白いと思ったかなどを共有しましょう。

分からないことがあれば、遠慮なく質問してください。試行錯誤を楽しんでください！
