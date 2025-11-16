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

# Workshop 05:<br>TidalCycles Practical Tutorial 2<br> Chords and Scale.

---

## 音符と旋律

---

### ドラムからシンセサイザーへ

- シーケンスのパートは主にドラムなどのサンプリング (あらかじめ録音された音)
- このパートでは、ピアノやシンセサイザーのように音程のある楽器を使う

<img src="https://yoppa.org/wp-content/uploads/2025/11/Screenshot-2025-11-16-153805-scaled.png" width="640"/>

---

### 数字による音程の指定

```haskell
-- tidalcycles
d1 $ note "0 4 7 11" # s "superpiano" 
```
```javascript
// Strudel
note("48 52 55 59").sound("piano")
```

- 音符 (ノート) は note() で生成する
- 数値のシーケンスが音程 (音の高さ) になる
- 数値はMIDIノート番号
- ピアノの中心のド「C」は60 (TidalCyclesでは0)

---

<img src="https://www.audiolabs-erlangen.de/resources/MIR/FMP/data/C1/FMP_C1_MIDI-NoteNumbers.png" width="720"/>

---

### 文字(音階)による音符の指定

```haskell
-- tidalcycles
d1 $ note "c e g b" # s "superpiano" 
```
```javascript
// Strudel
note("c e g b").sound("piano")
```

- 英語の音階名で指定
- c (ド)、d (レ) 、e (ミ)、f (ファ)、g (ソ)、a (ラ)、b (シ)

---

### オクターブの指定
```haskell
-- tidalcycles
d1 $ note "c4 e4 g4 b4" # s "superpiano" 
```
```javascript
// Strudel
note("c4 e4 g4 b4").sound("piano")
```
- 音階名 + 数値: オクターブを指定

---

### 半音階 (シャープ・フラット)

フラット (♭) : 半音下げる

```haskell
-- tidalcycles
d1 $ note "c4 d4 ef4 g4" # s "superpiano"
```
```javascript
// Strudel
note("c4 d4 ef4 g4").sound("piano")
```
---

シャープ (♯) : 半音上げる

```haskell
-- tidalcycles
d1 $ note "c4 d4 e4 gs4" # s "superpiano"
```
```javascript
// Strudel
note("c4 d4 e4 gs4").sound("piano")
```

- フラット (半音下げ) : 音階名 + f
- フラット (半音下げ) : 音階名 + s

---

### 音色を変える

```haskell
-- tidalcycles
d1
  d1 $ note "c4 e4 g4 b4" # s "supersaw" 
```
```javascript
// Strudel
note("c4 e4 g4 b4").sound("supersaw")
```

- sound( ) の中身を別のものに変えてみる → 例: supersaw
- その他にも様々な音色が使用できる

---

### 音色のシーケンス

```haskell
-- tidalcycles
d1 
  $ note "c4 d4 e4 [g4, b4]"
  # s "superpiano supersaw"
```
```javascript
// Strudel
note("c4 d4 e4 [g4, b4]")
  .sound("piano gm_electric_guitar_muted")
```

- sound( ) の中で複数の楽器をスペースを挟んで列挙
- 音色が途中で切り替わる
- シーケンスを組んでいくことも可能

---

### 音色を重ねる

```haskell
-- tidalcycles
d1 
  $ note "c4 d4 e4 [g4, b4]"
  # s "superpiano, supersaw"
```
```javascript
// Strudel
note("c4 d4 e4 [g4, b4]")
  .sound("piano, gm_electric_guitar_muted")
```

- sound( ) の中をスペースでなくコンマ (, ) で区切る
- シーケンスではなく複数の楽器を同時に演奏
- 楽器のスタック

---

### 1シーケンスをサイクルごとに

```haskell
-- tidalcycles
d1 
  $ note "<[c3 g3]*4 [c3 f3]*4 [d3 g3]*4 [c3 c4]*4>/2"
  # s "supersaw"
```
```javascript
// Strudel
note("<[c3 g3]*4 [c3 f3]*4 [d3 g3]*4 [c3 c4]*4>/2")
  .sound("supersaw")
```

- 1サイクルずつシーケンスを変化
- < > で囲んだ部分でサブシーケンスを組んでいく
- 順番に演奏される!

---

### 交互に演奏

```haskell
-- tidalcycles
d1 
  $ note "[c3 <e3 f3 g3 b3>]*2"
  # s "supersaw"
```
```javascript
// Strudel
note("[c3 <e3 f3 g3 b3>]*2")
  .sound("supersaw")
```

- 通常のシーケンスと < > を組み合わせ
- 交互に演奏が変化、オルタネイト

---

### 音を引き伸ばす

```haskell
-- tidalcycles
d1 
  $ note "[c3@3 <e3 f3 g3 b3>]*2"
  # s "supersaw"
```
```javascript
// Strudel
note("[c3@3 <e3 f3 g3 b3>]*2")
  .sound("supersaw")
```

- 音階@数値 で音が引き伸ばされる
- @3 は3倍の長さ

---

### 音符を複製 (Replicate)

```haskell
-- tidalcycles
d1 
  $ note "[c3!3 <e3 f3 g3 b3>]*2"
  # s "supersaw"
```
```javascript
// Strudel
note("[c3!3 <e3 f3 g3 b3>]*2")
  .sound("supersaw")
```

- ! でノートを複製
- @ に似ているが音を伸ばさず区切る

---

## Let’s Try!

- ここまでの内容を駆使して、オリジナルのシーケンスを作成してみよう!
- ドラムサウンド、楽器、双方のミックス ...etc.