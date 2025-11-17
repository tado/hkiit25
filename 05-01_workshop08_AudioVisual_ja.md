# TouchDesigner実践 3 – オーディオビジュアル、音響の視覚化

June 5, 2025

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-175824.jpg?resize=1024%2C576&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-175824-scaled.jpg?ssl=1)

オーディオビジュアル（Audio Visual）とは、音（Audio）と映像（Visual）を組み合わせたメディアや技術全般を指す言葉です。

メディアアートの文脈では、単に音と映像を同時に扱うのではなく、両者を緊密に連携させることで統一感のある知覚体験を生み出す芸術形式を意味します。その根源には、キネティック・アブストラクト・アートのような動きを持つ抽象芸術と、音楽やサウンドが持つ時間的・構造的要素との関係性を探求する試みがあります。

空間全体で体験するアート・インスタレーション、リアルタイムで展開されるパフォーマンス、あるいは緻密に設計された映像作品など多岐にわたります。音のリズムが映像の動きを制御したり、映像の変化が新たな音を生み出したりと、その相互作用が鑑賞者の感覚に深く働きかけます。

今回は、このようなオーディオビジュアルな表現をTouchDesignerを用いて実現することを目指します。

## オーディオビジュアル参考作品

- [Synchromy Norman McLaren (1971)](https://www.youtube.com/embed/_UA40sL06sU?feature=oembed)
- [ALVA NOTO - UNIE-QAV #10 UNI EDIT](https://www.youtube.com/embed/27hiBK_c3Oc?feature=oembed)
- [Ryoji Ikeda - Live in London, 2023.11.8](https://www.youtube.com/embed/RK6WnfWWnec?feature=oembed)
- [New Rituals 2022 at Barbican Centre feat Ryoichi Kurokawa and Nkisi (Trailer)](https://www.youtube.com/embed/h99HUWoVyWE?feature=oembed)

## 音波 (Sound Wave) とは?

そもそも音波とは、音とは何なのか?

[Understanding Sound Waves | MED-EL](https://www.youtube.com/embed/XLfQpv2ZRPU?feature=oembed)

## 波形解析 – 基本 1: サウンドファイルの再生と波形の表示

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-151821.jpg?resize=1024%2C557&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-151821.jpg?ssl=1)

[ダウンロード](https://github.com/tado/tdexamples/blob/main/08-01_SoundWave.toe)

ポイント:

- TouchDesignerでは音は数値の連なりと捉える、よってサウンドデータにはCHOPを用いる
- サウンドファイルを読み込みにAudio File In CHOPを使用
- 読み込むだけではサウンドは再生されない、Audio Device Out CHOPに接続することで再生
- 音波のデータが格納されているCHOPをCHOP to TOPすると音を視覚的に捉えることが可能となる

## 波形解析 – 基本 2: サウンドの音量を視覚化する

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-04-121402.jpg?resize=1024%2C557&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-04-121402.jpg?ssl=1)

[ダウンロード](https://github.com/tado/tdexamples/blob/main/08-02_WaveCircles.toe)

ポイント:

- Audio File In CHOPで取得された音は、一定の範囲の音が格納されている (バッファリング)
- CHOPに格納された音のデータを数値として使用するには、Analize CHOPを使用して単一の数値化する必要がある
- Analyze CHOPには様々な解析方法が提供されている
  - Value of First Peak: バッファーの最初の値
  - Avarage: バッファー内の全ての値の平均
  - Maximum: 最大値
  - Minimum: 最小値
  - Sum: 合計値
  - RMS Power: 移動平均平方根
- 視覚化する際には、RMS Powerが向いている
- 一度数値化してしまえば、図形などの様々なパラメータへと適用できる
- Lag CHOP: 数値の変化をスムーズに補完する、急激なピークの変化を抑える
- Filter CHOP: 全体の変化をより滑らかにフィルタリングする (ローパスフィルタ)

## 波形解析 – 基本 3: フィルターの活用、周波数帯域に分けて視覚化

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-04-124458.jpg?resize=1024%2C557&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-04-124458.jpg?ssl=1)

[ダウンロード](https://github.com/tado/tdexamples/blob/main/08-03_AudioFilters.toe)

ポイント:

- オーディオ用のフィルタを使うことで、波形の周波数帯域ごとの成分を抽出
- フィルターには様々な種類が存在する
  - ローパスフィルター (LPF): 低域を通過させる、高域はカットされる
  - ハイパスフィルター (HPF): 高域を通過させる、低域はカットされる
  - バンドパスフィルタ (BPF): 一定の周波数領域を通過させる
- フィルターを用いて、元の音を、低域、中域、高域に分解
- それぞれをAnalize CHOPのRMS Powerで解析してビジュアライズしてみる
- 音楽の成分 (バスドラ、ハイハットなど) ごとの変化が観察できる

<img width="640" alt="img" src="https://i0.wp.com/www.allaboutcircuits.com/uploads/articles/Types_of_Filters.jpg?ssl=1">様々なフィルターの種類: ローパス(LPF)、ハイパス(HPF)、バンドパス(BPF)、バンドストップ

## 波形解析 – 基本 4: Audio Analysis COMPを使用する

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-041639.jpg?resize=1024%2C499&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-041639.jpg?ssl=1)

- 音の波形を周波数ごとに解析して値をなめらかに整える機能をより便利に簡単に使いたい
- 専用のCOMPが用意されている → Audio Analysis COMP
- Palette > Tools >AudioAnalysis からドラッグ&ドロップ
- とても高性能かつ簡単!
- これまでのプログラムと同じ機能が、すっきりシンプルに実装できる

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-043259.jpg?resize=1024%2C544&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-043259.jpg?ssl=1)

[ダウンロード](https://github.com/tado/tdexamples/blob/main/08-04_AudioAnalysis.toe)

ポイント

- 手動で解析していたパートを、Audio Analysis COMPに置き換え
- 必要に応じてパラメーターを調整して値を整える

## 波形解析 – 応用 1: 周波数帯域の視覚化を3Dで表現

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-041716.png?resize=1024%2C544&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-041716.png?ssl=1)

[ダウンロード](https://github.com/tado/tdexamples/blob/main/08-05_AudioFilters3D.toe)

- これまで2次元の円 (Circle TOP) で視覚化していたものを3Dへ
- この例では、ノイズで変形させた球 (Sphere SOP) を半透明の色を着色して変形させている
- いろいろなアイデアで多種多用な視覚化が可能
- これまでの講義の内容を応用してみる!

## 波形解析から周波数解析へ

なぜ周波数解析が必要なのか?

- FFT (高速フーリエ変換) : 音を周波数の成分に分解する → そもそも何故この操作が必要なのか?
- 耳が音を聴いている仕組みを考える

[Sound Stimulates the Cochlea | MED-EL](https://www.youtube.com/embed/wkHPXHB3OxQ?feature=oembed)

[Hearing, Ear Anatomy &amp; Auditory Transduction](https://www.youtube.com/embed/sSgZXrdlIlM?feature=oembed)

つまり私たちは音を周波数成分の分解して聴いている!

<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/cochlea.png?resize=688%2C484&ssl=1">引用: [Hearing, the cochlea, the frequency domain and Fourier’s series](https://uncommondescent.com/video/hearing-the-cochlea-the-frequency-domain-and-fouriers-series/)

### FFTとIFFT

- FFT (高速フーリエ変換) : 波形を周波数成分へ
- IFFT (高速フーリエ逆変換): 周波数成分を波形へ

<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Convolution_FFT_and_IFFT.jpg?resize=1251%2C412&ssl=1">

### STFT (短時間フーリエ変換)

実際に解析する際には、一定の時間で信号を切り取って解析していく

- 切り取る信号の時間 → FFT Length (2の累乗のサンプル数)
- 窓関数 (Windowing)

このFFT解析結果をプロットしたのがスペクトログラム (Spectrogram)

<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Spectrogram-19thC.png?resize=644%2C335&ssl=1">

参考: 【視覚的に理解する】フーリエ変換

[【視覚的に理解する】フーリエ変換](https://www.youtube.com/embed/fGos3wrKeHY?feature=oembed)

## FFT視覚化基本1: スペクトラムをTOPで視覚化

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-060137.png?resize=1024%2C544&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-060137.png?ssl=1)

[ダウンロード](https://github.com/tado/tdexamples/blob/main/08-06_FFTBasic.toe)

ポイント

- Aufio File In CHOPで取得した信号をAudio Spectrum CHOPに接続
- FFT解析が行われる
- 解析の際の様々なパラメータが設定可能
  - FFT Size (STFTで分割する際のサンプル数)
  - スケール (線形スケールからログスケール) の設定
  - 高周波成分の強調
- 解析結果を、CHOP to TOPでテクスチャーに
- 周波数成分がストライプ状に模様が浮かびあがる

## FFT視覚化基本2: 左右対象にして着色

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-173929.jpg?resize=1024%2C557&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-173929.jpg?ssl=1)

[ダウンロード](https://github.com/tado/tdexamples/blob/main/08-07_FFTVisStripe.toe)

- 周波数成分によってグラデーション状に着色 (Ramp TOPを掛け合せる)
- 左右のチャンネルを左右対象に配置
- 低域が中心、高域が左右の周囲に配置される

## FFT視覚化基本3: 円に変換

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-062212.jpg?resize=1024%2C544&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2025/06/Screenshot-2025-06-05-062212.jpg?ssl=1)

[ダウンロード](https://github.com/tado/tdexamples/blob/main/08-08_FFTVisCircle.toe)

ポイント

- Cartesian To Poloar COMP: デカルト座標から極座標に変化するCOMP
- ストライプ状のスペクトルのパターンを円環状に変換することが可能
- 左右の音が円のパターンとして表現される

## いろいろ詰めあわせ

いろいろ詰めあわせセットを作ってきました!

[<img width="640" alt="img" src="https://i0.wp.com/yoppa.org/wp-content/uploads/2024/06/Screenshot-2024-06-07-055236.png?resize=1024%2C563&ssl=1">](https://i0.wp.com/yoppa.org/wp-content/uploads/2024/06/Screenshot-2024-06-07-055236.png?ssl=1)

[ダウンロード](https://github.com/tado/tdexamples/blob/main/08-09_audioVisualFFT.toe)

## アンケート

本日のアンケートです

- [アンケート](https://forms.gle/He9o6Q76SrJRZPDD8)