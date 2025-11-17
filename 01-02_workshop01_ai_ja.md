# ワークショップ 01：生成AIと創造の未来

## イントロダクション

### ワークショップの目的

このワークショップでは、生成AIの基礎から応用まで幅広く扱い、創造におけるAIの可能性を探求します。テキスト、画像、音楽、映像、コード生成の実例を通じ、参加者はAIがクリエイティブな作業にどう活用できるかを体験します。アートやデザインにもたらす変革を探りつつ、その限界や課題についても批判的に考察します。

### 生成AIに対するスタンス

生成AIの出現は、インターネット検索エンジンの登場に似ています。

  * **強力な利便性**：「検索」から「相談」へのシフト。膨大なデータから新しいものを生成できます。
  * **問題点**：ハルシネーション（嘘）、著作権、情報漏洩、倫理的課題なども存在します。
  * **本ワークショップの立ち位置**：
      * AIを盲信したり、無批判に受け入れたりはしません。
      * しかし、拒絶するのではなく、問題や構造を**批判的に考え**ながら、その利便性を享受することが重要です。
      * まずは実際に触れて技術に積極的に関わり、正確な理解を目指します。

## 生成AIの基礎 - TransformerとLLM

### AI / ML / DL / GenAI の関係

  * **人工知能 (AI)**：人間の知能を模倣するコンピュータシステム。（最も広い概念）
  * **機械学習 (ML)**：データからパターンを学習するAIの一分野。
  * **ディープラーニング (DL)**：人間の脳をモデルにしたニューラルネットワークを使用するMLの手法。
  * **生成AI (GenAI)**：新しいコンテンツ（テキスト、画像、音楽など）を生成するDLの一部。
  * (参考動画: [Introduction to Generative AI](https://youtu.be/u3FQgoKEnZk?si=1ieVJ3BkRkKk38_d))

<img src = "https://i.ytimg.com/vi/G2fqAlgmoPo/maxresdefault.jpg" width = "480" />

### ChatGPTにつながる30年の歴史

  * **初期 (1980年代)**：リカレントニューラルネットワーク (RNN) が「記憶」の概念を導入し、系列学習（単語予測など）の研究が始まりました。
  * **転換点 (2017年)**：**Transformer**アーキテクチャが開発されました。
  * **進化 (2018-2020年)**：
      * **GPT-1**：Transformerを「次の単語予測」に応用。
      * **GPT-2**：Webから収集した大規模データで学習。
      * **GPT-3**：1750億パラメータ。ゼロショット学習（指示だけでタスクをこなすこと）が可能に。
  * (参考動画: [ChatGPT: 30 Year History | How AI Learned to Talk](https://youtu.be/OFS90-FX6pg?si=ju7SE-nF-FNRnB9s))

<img src = "https://i.ytimg.com/vi/OFS90-FX6pg/maxresdefault.jpg" width = "480" />

### LLMとTransformerの仕組み

  * **LLMの本質**：これらは**確率的に次の単語を予測する**数学的な関数です。

  * **Transformer**：

      * 以前のモデル（RNN）は単語を一つずつ処理していました。
      * Transformerはテキスト全体を**並列**に処理できます。

  * **Attention Mechanism (Attention)**：

      * Transformerの核心技術です。
      * 文中の各単語が他の単語とどれだけ強く関連しているかを計算します。
      * これにより、文脈に応じた意味（例：「bank」が金融機関か土手か）を理解可能にします。

  * **参考文献**：
    動画: [Large Language Models explained briefly](https://www.youtube.com/watch?v=LPZh9BOjkQs)

    <img src = "https://i.ytimg.com/vi/LPZh9BOjkQs/maxresdefault.jpg" width = "480" />

    図解ガイド: [The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/)

    <img src = "https://jalammar.github.io/images/t/transformer_resideual_layer_norm_3.png" width = "480" />

    インタラクティブ解説: [Transformer Explainer: LLM Transformer Model Visually Explained](https://poloclub.github.io/transformer-explainer/)

    <img src = "https://poloclub.github.io/transformer-explainer/article_assets/attention.png" width = "480" />
      

## ジェネラティブアートの歴史とAIアートの事例

### ジェネラティブアートとは？

  * **ジェネラティブアート**：アーティストが作品そのものを直接作るのではなく、作品を生成する「**ルール**」「**プロセス**」「**システム**」を定義する芸術です。
  * アルゴリズムやシステムが自律的に作品を生成します。
  * 現在の「**生成AI**」は、このジェネラティブアートの最新形態と見ることができます。
  * (参考動画: [What is Generative Art: TouchDesigner’s Role](https://www.youtube.com/watch?v=1RD83NjwNIk))

<img src = "https://i.ytimg.com/vi/1RD83NjwNIk/maxresdefault.jpg" width = "480" />

### ジェネラティブアートの歴史（抜粋）

(参考: [Generative Art Timeline](https://timeline.lerandom.art/))

  * **1950年代 (アナログ時代)**：ベン・ラポスキーがオシロスコープを使って「Electronic Abstractions」を制作。
  * **1960年代 (デジタル時代)**：フリーダー・ナケなどのアーティストが初期のコンピュータとプロッターでアルゴリズムによる描画を作成。
  * **1970年代 (アーティスト・プログラマー時代)**：ハロルド・コーエンがAIアートの先駆者「AARON」を開発。
  * **1990年代 (ネット時代)**：ジョン・マエダが「Design By Numbers」を発表。
  * **2000年代 (ツール化時代)**：**Processing**や**openFrameworks**が登場し、クリエイティブコーディングが普及。
  * **2010年代 (AI時代)**：Googleの**DeepDream** (2015) やGANが登場。
  * **2020年代 (オンチェーン / 拡散モデル時代)**：DALL-E (2021) やStable Diffusion (2021) が導入されました。

<img src = "https://pbs.twimg.com/media/FzO22nRaEAMPItv?format=jpg&name=4096x4096" width = "480" />  

### AIを活用したアート作品例

**[Refik Anadol, *Unsupervised* (2023)](https://refikanadol.com/works/unsupervised/)**

<img src = "https://dpk6zrxldcuco.cloudfront.net/2023/annual/professional/31079cd9-f223-477c-82fe-8a0b230a2c40/860x484q80-smart.jpg" width = "480" />

  * MoMA（ニューヨーク近代美術館）の全コレクションをAIに学習させ、新たな「機械の幻覚」をリアルタイムで生成し続ける作品。

**[Nao Tokui - AI DJ Project (2016)](https://qosmo.jp/art/ai-dj-human-dj-b2b)**

<img src = "https://www.naotokui.net/wp-content/uploads/2018/01/26A0877-800x533.jpg" width = "480" />

  * AIと人間のDJがB2B（バック・トゥ・バック）形式で、交互に選曲を行うプロジェクト。

**[The Beatles, *Now And Then* (2023)](https://youtu.be/AW55J2zE3N4?si=1A18nDsyifkysFAJ)**

<img src = "https://i.ytimg.com/vi/Opxhh9Oh3rg/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD\&rs=AOn4CLDToUSNIbJe9wSRyCjtebMv3j-HuQ" width = "480" />

  * AI技術を用いて古いデモテープからジョン・レノンのボーカルとピアノを分離。クリアになったボーカルを基に残りのメンバーが新たな演奏を加え、ビートルズ最後の新曲として完成させました。

### キュレーターの視点：何がアートと見なされるか？

<img src = "https://static01.nyt.com/images/2025/10/19/multimedia/19sp-finearts-AI-02-kvzt/19sp-finearts-AI-02-kvzt-articleLarge.jpg?quality=75\&auto=webp\&disable=upscale" width = "480" />

  * ニューヨーク・タイムズの記事「[Amid the A.I. Deluge, What Counts as Art?](https://www.nytimes.com/2025/10/18/arts/design/artificial-intelligence-art-museums.html)」によると、多くのキュレーターはAIアートの価値を技術的新規性ではなく、その背後にあるアーティストの「**意図**」と「**プロセス**」に見出しています。
  * MoMAのキュレーターは、「技術がアートなのではない。最終的に重要なのは**個人の創造性とビジョン**だ」と述べています。
  * アーティストがAIモデルの構築やデータの選定に深く関わっている作品は、特に高く評価されます。

## 生成AIを活用したクリエイティブワークショップ

### 4-1. 画像生成（実践）

テキストから画像を生成するAIです。多様なスタイルや指示に対応できます。

  * **主なサービス**：

      * **[Google ImageFX](https://labs.google/fx/tools/image-fx)**：高品質でリアルな画像が得意。無料で利用可能。
      * **[DALL-E 3 (in ChatGPT)](https://chatgpt.com)**：指示への忠実度が高く、テキストの描画に優れています。
      * **[Midjourney](https://www.midjourney.com)**：芸術的で幻想的な品質が非常に高い。Discord経由で利用（有料）。
      * **[Stable Diffusion](https://stability.ai/stable-image)**：オープンソース。ローカル環境での実行が可能で、カスタマイズ性が最も高い。

  * **実践**：

      * **ツール**：[Google ImageFX](https://labs.google/fx/tools/image-fx) または [DALL-E 3 (in ChatGPT)](https://chatgpt.com/)
      * **プロンプト/タスク**：
        1.  シンプルなプロンプトを試す。
              * 例：`宇宙服を着た猫の油絵`
        2.  ImageFXの「Expressive chips」（太字の単語）を変更してバリエーションを見る。
              * 例：`**サイバーパンクな**宇宙服を着た**怒った**猫の**印象派の**絵画`
        3.  (DALL-E 3の場合) 会話形式で修正してみる。
              * 例：`猫をもっと大きくして、背景を月に変えて`

### 4-2. 映像生成（実践）

テキストや画像から動画を生成するAIです。急速に進化している分野です。

  * **技術の進化**：

      * **GAN (〜2019)**：リアルだが不安定な映像（例：[Deep Dream](https://github.com/google/deepdream)スタイル）。
      * **拡散モデル + Transformer (現在)**：ノイズから高品質な動画を生成。SoraやVeoはこの技術に基づいています。

  * **主なサービス**：

      * **[OpenAI Sora](https://sora.com/)**: 物理法則を理解し、高解像度の動画（1分以上）と音声を生成（アクセス制限あり）。
      * **[Google Veo (in Flow)](https://labs.google/flow)**：映画的な言語の理解に優れています（アクセス制限あり）。
      * **[Luma AI Dream Machine](https://lumalabs.ai)**：高速で使いやすく、高品質（無料枠あり）。
      * **[Pika](https://pika.art)**：クリエイティブなエフェクトやアニメ風の変換が得意（無料枠あり）。

  * **実践**：

      * **ツール**：[Luma AI Dream Machine](https://lumalabs.ai) または [Google Veo (in Flow)](https://labs.google/flow)
      * **プロンプト/タスク**：
        1.  テキストから動画を生成する。
              * 例：`トレンチコートを着たアライグマの探偵が、雨の降るネオン街を歩いている映画のようなショット。`
        2.  (画像がある場合) 画像をアップロードして動かしてみる。
              * 例：先ほど生成した「宇宙服を着た猫」の画像を動かしてみてください。

### 4-3. 音楽生成（実践）

テキスト（歌詞や雰囲気）から、ボーカルと伴奏を含む完全な楽曲を生成するAIです。

  * **主なサービス**：

      * **[Suno AI](https://suno.com/)**: 日本語の歌詞にも対応。ジャンルやスタイルを指定して高品質な楽曲（ボーカル入り）を生成。
      * **[Google MusicFX DJ](https://aitestkitchen.withgoogle.com/tools/music-fx-dj)**：楽器、ジャンル、雰囲気を組み合わせて、リアルタイムで音楽生成とリミックスが可能。

  * **実践**：

      * **ツール**：[Suno AI](https://suno.com/), [Google MusicFX DJ](https://aitestkitchen.withgoogle.com/tools/music-fx-dj)
      * **プロンプト/タスク**：
        1.  「Custom Mode」をオンにする。
        2.  **歌詞**を入力する（日本語OK）。
              * 例：
                ```
                (Aメロ)
                雨上がりのアスファルト
                ネオンが滲む夜
                (サビ)
                AIが見る夢は
                電気羊のメロディ
                ```
        3.  **音楽のスタイル**を指定する。
              * 例：`シティポップ, 80年代歌謡曲, ローファイ`
        4.  生成された2つのバリエーションを聴き比べる。

### 4-4. プログラミング（実践）

AIによるコードの生成、補完、デバッグ（エラー修正）の支援です。

  * **題材**: **[p5.js](https://p5js.org/)**

      * ビジュアルアートのためのプログラミング言語。Webブラウザ上で直接実行できます。

  * **主なAIツール**：

      * **ChatGPT**: 最も手軽な方法。「p5.jsで〜するコードを書いて」と頼めます。
      * **[p5.CodingWithAI](https://app.kyabe.net/p5-coding-with-ai/)**: 専用のp5.jsエディタ。AIと対話しながらコードを洗練できます。
      * **[Github Copilot](https://github.com/features/copilot)**: VSCodeなどのエディタに統合。プロ向けの強力なコード補完・生成ツール。

  * **実践**：

      * **ツール**：[ChatGPT](https://chatgpt.com/) + **[p5.js Web Editor](https://editor.p5js.org/)** または [p5.CodingWithAI](https://app.kyabe.net/p5-coding-with-ai/)
      * **プロンプト/タスク**：
        1.  ChatGPTに初期コードを生成させる。
              * プロンプト：`p5.jsを使って、マウスの位置に追従して円を描くプログラムを作ってください。背景は黒にしてください。`
        2.  生成されたコードをp5.jsエディタにコピー＆ペーストして実行する。
        3.  ChatGPTに追加の指示を出して修正する。
              * プロンプト：`マウスをクリックした時に、円の色がランダムに変わるように変更してください。`
        4.  修正されたコードを再度実行して結果を確認する。

## 結論

### 生成AIと創造の未来

  * **AIはツールか、コラボレーターか？**：
      * 今日の実践で見たように、AIはアイデアを形にするための強力な「ツール」です。
      * 同時に、人間の意図を汲み取り、予期せぬ提案をしてくれる「コラボレーター」にもなり得ます。
  * **人間の役割**：
      * 「何を作るか」という**ビジョン**と、問いを立てる力。
      * AIのアウトプットを**評価・選択**し、修正指示を出す「編集」能力。
      * AIが学習していない新しい**文脈**や**プロセス**を設計する力。
  * **課題**：データのバイアス、著作権、エネルギー消費など、技術の背後にある問題を批判的に見つめ続ける必要があります。