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

# ワークショップ 01: 生成AIと創作の未来

-----

## はじめに

### ワークショップの目的

本ワークショップでは、生成AIの基礎から応用までを幅広く学び、創作におけるAIの可能性を探求します。テキスト、画像、音楽、映像、コード生成などの実例を通して、AIがどのように創作に活用できるかを体験します。AIがアートやデザインにもたらす変革を探ると同時に、その限界や課題についても批判的に考察します。

-----

### 生成AIへのスタンス

生成AIの登場は、インターネット検索エンジンの登場時と似ています。

  * **強力な利便性**: 「検索」から「相談」へ。膨大なデータから新たなものを生成可能です。
  * **問題点**: ハルシネーション（嘘）、著作権、情報漏洩、倫理的な課題も存在します。
  * **本ワークショップの立場**:
      * AIを盲信したり、無批判に受け入れたりするわけではありません。
      * しかし、拒否するのでもなく、その利便性を享受しつつ、問題や構造について**批判的に考えていく**ことが重要です。
      * まずは技術について正確なイメージを持つために、積極的に触れて試していきます。

-----

## 生成AIの基礎知識 - TransformerとLLM

-----

### AI / ML / DL / GenAI の関係

  * **人工知能 (AI)**: 人間の知能を模倣するコンピューターシステム。（最も広い概念）
  * **機械学習 (ML)**: データからパターンを学習するAIの一分野。
  * **深層学習 (DL)**: 人間の脳神経を模したニューラルネットワークを用いるMLの手法。
  * **生成AI (GenAI)**: 新しいコンテンツ（テキスト、画像、音楽など）を生成するDLの一部。
  * (参考動画: [Introduction to Generative AI](https://youtu.be/u3FQgoKEnZk?si=1ieVJ3BkRkKk38_d))

-----

### ChatGPTに至る30年の歴史

  * **初期 (1980s)**: 再帰型ニューラルネットワーク (RNN) が「記憶」の概念を導入し、順序学習（例：単語の予測）の研究が始まりました。
  * **転換点 (2017)**: **Transformer** アーキテクチャが開発されました。
  * **進化 (2018-2020)**:
      * **GPT-1**: Transformerを「次の単語予測」に適用しました。
      * **GPT-2**: Webから収集した大規模データで学習しました。
      * **GPT-3**: 1750億パラメータ。ゼロショット学習（指示だけでタスク実行）が可能になりました。
  * (参考動画: [ChatGPT: 30 Year History | How AI Learned to Talk](https://youtu.be/OFS90-FX6pg?si=ju7SE-nF-FNRnB9s))

-----

### LLMとTransformerの仕組み

  * **LLMの本質**: 次に来る単語を**確率的に予測する**数学的関数です。
  * **Transformer**:
      * かつてのモデル（RNN）は1単語ずつ処理していました。
      * Transformerは、テキスト全体を**並列処理**できます。
  * **アテンション機構 (Attention)**:
      * Transformerの核となる技術です。
      * 文中の各単語が、他のどの単語と強く関連しているかを計算します。
      * これにより、文脈に合った意味を理解できます（例: 「バンク」が「銀行」なのか「川岸」なのかを判断）。

---

  * **参考資料**:
      * 動画: [LLMの仕組み（簡単バージョン）](https://www.youtube.com/watch?v=y7NQiNER6r4)
      * 図解: [The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/)
      * インタラクティブ: [TRANSFORMER EXPLAINER](https://poloclub.github.io/transformer-explainer/)

-----

## 生成芸術の歴史とAI作品事例

-----

### 生成芸術 (Generative Art) とは？

  * **生成芸術 (Generative Art)**: アーティストが作品そのものを直接制作するのではなく、作品が生成される「**ルール**」や「**プロセス**」、「**システム**」を設定する芸術です。
  * アルゴリズムやシステムが、自律的に作品を生成します。
  * 現在の「**生成AI**」は、この生成芸術の最新の形態と捉えることができます。
  * (参考動画: [What is Generative Art: TouchDesigner’s Role](https://www.youtube.com/watch?v=1RD83NjwNIk))

-----

### 生成芸術の歴史 (抜粋)

(参考資料: [Generative Art Timeline](https://timeline.lerandom.art/))

  * **1950s (アナログ時代)**: ベン・ラポスキーがオシロスコープで『Electronic Abstractions』を制作しました。
  * **1960s (デジタル時代)**: フリーダー・ナーケらが初期のコンピューターとプロッター（描画機）でアルゴリズムによるドローイングを制作しました。
  * **1970s (アーティスト・プログラマー時代)**: ハロルド・コーエンがAIアートの先駆け『AARON』を開発しました。

---

  * **1990s (ネット時代)**: ジョン・マエダが『Design By Numbers』を発表しました。
  * **2000s (ツール時代)**: **Processing** や **openFrameworks** が登場し、クリエイティブ・コーディングが普及しました。
  * **2010s (AI時代)**: Googleの**DeepDream** (2015) やGANが登場しました。
  * **2020s (オンチェーン / 拡散モデル時代)**: DALL-E (2021)、Stable Diffusion (2021) が登場しました。

-----

### AIを用いた芸術作品の事例

  * **[Refik Anadol, *Unsupervised* (2023)](https://refikanadol.com/works/unsupervised/)**
      * MoMA（ニューヨーク近代美術館）のコレクション全作品をAIに学習させ、リアルタイムで新たな「機械の幻覚」を生成し続ける作品です。
  * **[徳井直生 - AI DJ Project (2016)](https://qosmo.jp/art/ai-dj-human-dj-b2b)**
      * AIと人間のDJがB2B（交互に選曲）形式でパフォーマンスするプロジェクトです。
  * **[The Beatles, *Now And Then* (2023)](https://youtu.be/AW55J2zE3N4?si=1A18nDsyifkysFAJ)**
      * AI技術を使用し、ジョン・レノンの古いデモテープからボーカルとピアノの音を分離しました。クリアになったボーカルを基に、残りのメンバーが演奏を加え、ビートルズ最後の新曲として完成させました。

-----

### キュレーターの視点：何がアートか？

  * The New York Timesの記事「[AIの氾濫の中で、何がアートにあたるのか？](https://www.nytimes.com/2025/10/18/arts/design/artificial-intelligence-art-museums.html)」 によると、多くのキュレーターは、AIアートの価値を技術的な目新しさではなく、その背後にあるアーティストの「**意図**」や「**プロセス**」にあると考えています。
  * MoMAのキュレーターは「テクノロジーがアートなのではなく、最終的には**個人の創造性とビジョン**が重要だ」と述べています。
  * 特に、アーティスト自身がAIモデルの構築や学習データの選別に深く関わる作品が高く評価されています。

-----

## 生成AIを活用した創作ワークショップ

-----

### 4-1. 画像生成（実習）

テキストから画像を生成するAIです。様々なスタイルや指示に対応可能です。

  * **主なサービス**:
      * **[Google ImageFX](https://labs.google/fx/tools/image-fx)**: 高品質でリアルな画像が得意です。無料で利用可能です。
      * **[DALL-E 3 (ChatGPT内)](https://chatgpt.com)**: 指示への忠実度が高く、テキスト描画が得意です。
      * **[Midjourney](https://www.midjourney.com)**: 芸術的・幻想的な品質が非常に高いです。Discord経由で使用します（有料）。
      * **[Stable Diffusion](https://stability.ai/stable-image)**: オープンソースです。ローカル環境で実行でき、カスタマイズ性が最も高いです。

-----

### 4-1. 画像生成（実習）

  * **実習**:
      * **ツール**: [Google ImageFX](https://labs.google/fx/tools/image-fx) または [DALL-E 3 (ChatGPT内)](https://chatgpt.com/)
      * **お題**:
        1.  簡単なプロンプトを試す。
              * 例: `油絵風の、宇宙服を着た猫`
        2.  ImageFXの「表現力チップ」（太字の単語）を色々変えて、変化を試す。
              * 例: `**印象派**風の、**サイバーパンクな**宇宙服を着た、**怒っている**猫`
        3.  （DALL-E 3の場合）対話形式で修正してみる。
              * 例: `もっと猫を大きくして、背景を月に変えて`

-----

### 4-2. 動画生成（実習）

テキストや画像から動画を生成するAIです。急速に進化している分野です。

  * **技術の進化**:
      * **GAN (〜2019)**: リアルだが不安定な映像（例: [Deep Dream](https://github.com/google/deepdream)風）。
      * **拡散モデル + Transformer (現在)**: ノイズから高品質な映像を生成します。SoraやVeoはこの技術がベースです。

---

  * **主なサービス**:
      * **[OpenAI Sora](https://sora.com/)**: 物理法則を理解し、1分以上の高解像度動画と音声を生成します（限定公開中）。
      * **[Google Veo (Flow内)](https://labs.google/flow)**: 映画的な表現言語の理解に優れます（限定公開中）。
      * **[Luma AI Dream Machine](https://lumalabs.ai)**: 高速で使いやすく、品質も高いです（無料枠あり）。
      * **[Pika](https://pika.art)**: クリエイティブなエフェクトやアニメ調の変換が得意です（無料枠あり）。

-----

### 4-2. 動画生成（実習）

  * **実習**:
      * **ツール**: [Luma AI Dream Machine](https://lumalabs.ai)、[OpenAI Sora](https://sora.com/)、[Google Veo](https://labs.google/flow) など
      * **お題**:
        1.  テキストから動画を生成する。
              * 例: `A cinematic shot of a raccoon detective in a trench coat, walking through a rainy neon-lit city street at night.`
        2.  （もし手持ちの画像があれば）画像をアップロードし、動きをつけてみる。
              * 例: 先ほど画像生成AIで作った「宇宙服の猫」の画像を動してみる。

-----

### 4-3. 音楽生成（実習）

テキスト（歌詞や雰囲気）からボーカルや伴奏を含む楽曲を生成するAIです。

  * **主なサービス**:
      * **[Suno AI](https://suno.com/)**: 日本語の歌詞にも対応しています。ジャンルやスタイルを指定して高品質な楽曲（ボーカル含む）を生成します。
      * **[Google MusicFX DJ](https://aitestkitchen.withgoogle.com/tools/music-fx-dj)**: 楽器、ジャンル、感情などを組み合わせてリアルタイムに音楽を生成・リミックスできます。

-----

### 4-3. 音楽生成（実習）

  * **実習**:
      * **ツール**: [Suno AI](https://suno.com/)
      * **お題**:
        1.  「カスタムモード」をオンにします。
        2.  **歌詞 (Lyrics)** を入力します              
        3.  **スタイル (Style of Music)** を指定します。
              * 例: `City Pop, 80s Japanese, Lo-fi`
        4.  生成された2パターンの曲を聴き比べます。

-----

### 4-4. プログラミング（実習）

AIがコードの生成、補完、デバッグ（エラー修正）を支援します。

  * **題材**: **[p5.js](https://p5js.org/)**
      * ビジュアルアートのためのプログラミング言語です。Webブラウザで実行可能です。
  * **主なAIツール**:
      * **ChatGPT**: 最も手軽です。「p5.jsで〜するコードを書いて」と質問できます。
      * **[p5.CodingWithAI](https://app.kyabe.net/p5-coding-with-ai/)**: p5.js専用エディタです。AIと対話しながらコードを改良できます。
      * **[Github Copilot](https://github.com/features/copilot)**: VSCodeなどのエディタに統合されています。プロ向けの強力なコード補完・生成ツールです。

-----

### 4-4. プログラミング（実習）

  * **実習**:
      * **ツール**: [ChatGPT](https://chatgpt.com/) + **[p5.js Web Editor](https://editor.p5js.org/)** または [p5.CodingWithAI](https://app.kyabe.net/p5-coding-with-ai/)
      * **お題**:
        1.  ChatGPTに最初のコードを生成させます。
              * プロンプト: `p5.jsを使って、マウスの位置についてくる円を描くプログラムを作成してください。背景は黒にしてください。`
        2.  生成されたコードを p5.js Editor にコピー＆ペーストして実行します。
        3.  ChatGPTに追加の指示を出して改良します。
              * プロンプト: `円の色を、マウスをクリックしたらランダムに変わるように変更してください。`
        4.  変更後のコードを再度実行し、変化を確認します。

-----

## まとめ

### 生成AIと創作の未来

  * **AIはツールか、協力者か？**:
      * 本日の実習のように、AIはアイデアを形にする強力な「ツール」です。
      * 同時に、人間の意図を汲み取り、予想外の提案をする「協力者」にもなり得ます。
  * **人間の役割**:
      * 「何を創りたいか」という**ビジョン**と「問い」を立てる力。
      * AIの出力を**評価・選別**し、改良の指示を出す「編集」能力。
      * AIが学習していない、新しい**文脈**や**プロセス**を設計する力。
  * **課題**: データの偏り、著作権、エネルギー消費など、技術の背後にある問題を批判的に見続ける必要があります。