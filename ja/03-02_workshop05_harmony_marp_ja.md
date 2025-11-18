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

---

## コード(chord、和音)とスケール(scale、音階)

---

### 同時に音を鳴らす

[ ] で囲ってコンマで区切ると同時に音が鳴る → リスト
```haskell
-- TidalCycles
d1
  $ s "superpiano*4"
  # note "[c, e, g]“
```
```javascript
// Strudel
note("[c, e, g]").sound("piano*4")
```

---

### コード (Chord = 和音) を演奏する

コード (Chord = 和音) とは?
複数 (通常は3音以上) の音程の音を同時に発音すること

<img src="https://jp.yamaha.com/files/ocp/ja_jp/services/teachers/music_pal/study/chord/code1_05.gif"/><br>
<img src="https://jp.yamaha.com/files/ocp/ja_jp/services/teachers/music_pal/study/chord/code1_06.gif"/>

---

### コードネームでリストを生成 → 和音へ

```haskell
-- TidalCycles
d1
  $ s "superpiano*4" 
  # note "c'maj"
```
```javascript
// Strudel
$: sound("piano*4")
  .n("[1, 2, 3, 4]")
  .chord("C").voicing()
```
---

### いろいろなコードを試してみる

```haskell
-- TidalCycles
d1
  $ s "superpiano*4" 
  # note "<c'maj f'maj g'maj c'maj>“

-- よりきれいにボイシング
d1
  $ s "superpiano"
  # note "<c5'maj f4'maj'ii g4'dom7'ii c5'maj'i>"
```
```javascript
//Strudel
$: sound("piano*4")
  .n("[1, 2, 3, 4]")
  .chord("<C F G C>").voicing()
```

---

### カノン進行 - C, G, Am, Em, F, C, F, G

```haskell
-- TidalCycles
d1
  $ s "superpiano*2" 
  # note "<c'maj g'maj a'min e'min f'maj c'maj f'maj g'maj>“

-- カノン進行 きれいにボイシング
d1
  $ s "superpiano*2" 
  # note "<c4'maj'ii g4'maj a3'min'ii e4'min f4'maj c4'maj f4'maj g3'dom7'iii>"  
```
```javascript
//Strudel
$: sound("piano*4")
  .n("[0, 1, 2, 3, 4]")
  .chord("<C G Am Em F C F G>").voicing()
```

---

### 王道進行 (J-POP風) - F△7–G7–Em7–Am

```haskell
-- TidalCycles
d1 
  $ s "superpiano*2"
  # note "<f5'maj7 g4'dom7'ii e5'min7 a4'min'ii>"
```
```javascript
//Strudel
$: sound("piano*2")
  .n("[1, 2, 3, 4, 5]")
  .chord("<FM7 G7 Em7 Am>").voicing()
```

---

### 王道進行アンサンブル

```haskell
-- TidalCycles
do
  d1
    $ s "supersaw(11, 16)"
    # note "<f5'maj7 g4'dom7'ii e5'min7 a4'min'ii>"
    # lpf (range 2000 8000 $ slow 16 $ sine)  
    # resonance 0.2
    # room 0.5 # size 0.8
  d2
    $ s "supersaw(9, 16)" 
    # note "<f2 g2 e2 a2>"
    |+ note "<0 12>*8"
    # lpf (range 1000 8000 $ slow 12 $ sine)
    # resonance 0.2
    # gain 1.5
  d3
    $ s "[bd(3, 8), hc(4, 8, 1)]"
    # gain 1.5
```
---

```javascript
// Strudel
$: sound("supersaw(11, 16)")
  .n("[1, 2, 3, 4, 5]")
  .chord("<FM7 G7 Em7 Am>").voicing()
  .lpf(sine.slow(32).range(1000, 8000)).resonance(10)
  .room(0.9)
$: sound("supersaw(9, 16)")
  .note("<F2 G2 A2 E2>".add("<-12 0 12>*4"))
  .lpf(sine.slow(24).range(1000, 8000)).resonance(8)
  .room(0.9).gain(1.8)
$: sound("bd(3, 8), hh(4, 8, 1)").bank("RolandTR909")
  .gain(1.2)
```
---

### 王道進行アンサンブル + 分数コード

```haskell
--- TidalCycles
do
  d1
    $ s "supersaw(11, 16)"
    # note "<f5'maj7 g4'dom7'ii e5'min7 a4'min'ii>"
    # lpf (range 1000 8000 $ slow 16 $ sine)  
    # resonance 0.2
    # room 0.5 # size 0.8
  d2
    $ s "supersaw(9, 16)" 
    # note "<f2 e2 d2 c2>/2"
    |+ note "<0 12>*8"
    # lpf (range 1000 8000 $ slow 12 $ sine)
    # resonance 0.2
    # gain 1.5
  d3
    $ s "[bd(3, 8), hc(4, 8, 1)]"
    # gain 1.5
```
---

```javascript
// Strudel
$: sound("supersaw(9, 16, 3)")
  .n("[1, 2, 3, 4, 5]")
  .chord("<FM7 G7 Em7 Am>").voicing()
  .lpf(sine.slow(32).range(1000, 8000)).resonance(10)
  .room(0.9)
$: sound("supersaw(9, 16)")
  .note("<F2 E2 D2 [C2 A1]>/2".add("<-12 0 12>*4"))
  .lpf(sine.slow(24).range(1000, 4000)).resonance(10)
  .gain(1.8)
$: sound("bd(4, 8), hh(4, 8, 1)").bank("RolandMC303")
  .delay(0.5).delaytime(3/8)
  .gain(1.3)
```
---

## スケール (旋法)

---

### スケール (旋法) とは

- 音楽で使用される音の集まりを体系的に並べたもの
- 音楽作品の基礎を形成し、曲の雰囲気や特徴を決定づける重要な要素
- 代表的なスケール
  - メジャースケール（長音階）
  - マイナースケール（短音階）
  - モード（旋法）※ 後述
  - ペンタトニックスケール（五音音階）
  - クロマティックスケール（半音階）

---  

### モード・ジャズ (Modal Jazz)

- 特定のモード（音階）を基盤に即興演奏を展開するジャズのスタイル
- 従来のコード進行に依存しない
- モードの特徴的な音と雰囲気を活かした自由なアプローチが特徴
  - 例: Miles Davis “Kind of Blue”
  - Dドリアンモード → E♭ドリアンモード → Dドリアンモード
  - [Spotify: Modal Jazz](https://open.spotify.com/playlist/0QNQ7nG51z51BVsciP99SU?si=e50cf7e04f9149a4&nd=1&dlsi=4663664f16aa4c52)

---

### 7つのモード

Ionian（イオニアン）Dorian （ドリアン）Phrygian（フリジアン）Lydian（リディアン）Mixolydian（ミクソリディアン）Aeolian（エオリアン）Locrian（ロクリアン）

<img src="https://www.shockwave-sound.com/blog/wp-content/uploads/2018/06/7Modes.jpg" width="720"/>

---

### スケールを演奏する

イオニアン (Ionian) スケール

```haskell
-- TidalCycles
d1
  $ s "supersaw*8"
  # note (scale "ionian" "[0..7]")
```
```javascript
// Strudel
$: sound("piano*8")
  .n("0 1 2 3 4 5 6 7")
  .scale("C:ionian")
```
---

### 定義済みのスケール

大量にスケールが定義されている! 試してみよう!

```
-- TidalCycles
minPent majPent ritusen egyptian kumai hirajoshi iwato
chinese indian pelog prometheus scriabin gong shang jiao
zhi yu whole augmented augmented2 hexMajor7 hexDorian
hexPhrygian hexSus hexMajor6 hexAeolian major ionian
dorian phrygian lydian mixolydian aeolian minor locrian
harmonicMinor harmonicMajor melodicMinor
melodicMinorDesc melodicMajor bartok hindu todi purvi
marva bhairav ahirbhairav superLocrian romanianMinor
hungarianMinor neapolitanMinor enigmatic spanish
leadingWhole lydianMinor neapolitanMajor locrianMajor 
diminished diminished2 chromatic
```
---
```
// Strudel
major pentatonic, major, minor, major blues, minor
blues, melodic minor, harmonic minor, bebop, diminished, 
dorian, lydian, mixolydian, phrygian, locrian, ionian
pentatonic, mixolydian pentatonic, ritusen, egyptian, 
neopolitan major pentatonic, vietnamese 1, pelog, 
kumoijoshi, hirajoshi, iwato, in-sen, lydian pentatonic, 
malkos raga, locrian pentatonic, minor pentatonic, minor 
six pentatonic, flat three pentatonic, flat six 
pentatonic, scriabin, whole tone pentatonic, lydian #5P 
pentatonic, lydian dominant pentatonic, minor #7M 
pentatonic, super locrian pentatonic, minor hexatonic, 
augmented, piongio, prometheus neopolitan, prometheus, 
mystery #1, six tone symmetric, whole tone, 
messiaen's mode #1, messiaen's mode #5, locrian major, 
double harmonic lydian, altered, locrian #2, mixolydian 
b6, lydian dominant, lydian augmented, dorian b2, 
ultralocrian, locrian 6, augmented heptatonic, dorian 
#4, lydian diminished, leading whole tone, lydian minor, 
phrygian dominant, balinese, neopolitan major, harmonic 
major, double harmonic major, hungarian minor, hungarian 
major, oriental, flamenco, todi raga, persian, 
enigmatic, major augmented, lydian #9, messiaen's mode 
#4, purvi raga, spanish heptatonic, bebop minor, bebop 
major, bebop locrian, minor bebop, ichikosucho, minor 
six diminished, half-whole diminished, kafi raga, 
messiaen's mode #6, composite blues, messiaen's mode #3, 
messiaen's mode #7, chromatic
```
---

### スケールをランダムに演奏する

```haskell
-- TidalCycles
d1
  $ s "superpiano*8"
  # note (scale "hirajoshi" (irand 12))
```
```javascript
// Strudel
$: sound("piano*8")
  .n(irand(12))
  .scale(“C:hirajoshi")
```

---

### スケールによる即興演奏

```haskell
-- TidalCycles
do
  let mode = "minPent"
  let root = "c"
  d1
    $ jux (("[10, 5]"/8)<~)
    $ s "superhammond(7, 8, [0, 5])"
    # voice 4
    # note "c2"
    |+ note (scale mode (irand 24))
    |+ note root
    # room 0.8 # size 0.9
  d2
    $ s "superhammond*16"
    # voice 3
    # note "c5"
    |+ note (scale mode (irand 7))
    |+ note root
    # room 0.8 # size 0.9
```

---

```javascript
$: sound("supersaw(5, 8)")  
  .n(irand(12))
  .scale("C1:hirajoshi").jux(rev).room(0.8)
  .delay(0.7).delaytime(3/8)
  .lpf(rand.range(400, 2000)).resonance(12)
$: sound("gm_church_organ*16")  
  .n(irand(19))
  .scale("C3:hirajoshi").jux(rev).room(0.8)
  .lpf(rand.range(400, 8000)).resonance(15)
  .delay(0.7).delaytime(5/8)
```