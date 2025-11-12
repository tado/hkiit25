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

# Workshop 2: TidalCyclesインストールパーティー

---

このセッションでは、これからのワークショップでメインで使用していくライブコーディング環境であるTidalCyclesのインストールを行います。

TidalCyclesはHaskellというプログラミング言語で書かれたライブラリで、音楽をコードで表現し、リアルタイムで演奏することができます。

インストールは少し手間がかかる場合があります。ステップバイステップで進めていきましょう!

---

## インストールの概要

### 対応OS

- macOS
- Windows
- Linux

---

### 自動インストールと手動インストール

TidalCyclesのインストールには、以下の2つの方法があります。

- **自動インストール**:
  インストールするOSに応じたパッケージマネージャーを使用して、必要なソフトウェアを一括でインストールします（推奨）。
- **手動インストール**:
  各ソフトウェアを個別にインストールします。自動インストールで問題が発生した場合や、特定の設定が必要な場合に試します。

---

## インストール - MacOS

---

### 自動インストール

以下の手順でTidalCyclesをインストールします。

**1. 事前準備: Apple Xcode command line toolsのインストール**

ターミナルを開き、以下のコマンドを実行します。

```bash
xcode-select --install
````

---

**2. tidal-bootstrapスクリプトの実行**

ターミナルで以下のコマンドを実行します。

```bash
curl https://raw.githubusercontent.com/tidalcycles/tidal-bootstrap/master/tidal-bootstrap.command -sSf | sh
```

インストールにはとても時間がかかります\! 辛抱強く待ちましょう。

---

この操作によって以下のソフトウェアがインストールされます。

  - [Haskell Language](https://www.haskell.org/) (Ghcup)
  - [cabal](https://www.haskell.org/cabal/): package system for Haskell and Tidalcycles
  - The Tidal Pattern engine (Tidal Cycles itself)
  - [Pulsar](https://pulsar-edit.dev/): Text editor
      - [tidalcycles plugin](https://github.com/tidalcycles/pulsar-tidalcycles) for Pulsar
  - [SuperCollider](https://supercollider.github.io/) for backend audio generation, and:
      - [SuperDirt](https://github.com/musikinformatik/SuperDirt): sample library used by tidal
      - [sc-3 plugins](https://github.com/supercollider/sc3-plugins): unit generator plugins

---

### トラブルシューティング

もしインストール中にエラーが発生した場合、以下のドキュメントを参照して個別に対応してください。

  - [TidalCyclds \> Installation \> macOS](https://tidalcycles.org/docs/getting-started/macos_install)

---  

### 手動インストール

もし自動インストールがうまくいかない場合は、以下のドキュメントを参照して手動でインストールしてください。

  - [TidalCyclds \> Installation \> macOS\#manual-installation](https://tidalcycles.org/docs/getting-started/macos_install#manual-installation)

---

## インストール - Windows

---

### 自動インストール

**1. 管理者としてpowershellを実行**

**2. Chocolateyのインストール**

以下のコマンドを実行します。

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

---

**3. TidalCyclesのインストール**

（Chocolateyのインストール後）以下のコマンドを実行します。

```powershell
choco install tidalcycles
```

インストールにはとても時間がかかります\! 辛抱強く待ちましょう。

---

この操作によって以下のソフトウェアがインストールされます。

  - [git](https://git-scm.com/)
  - [SuperCollider](https://supercollider.github.io/)
  - [sc3-plugins](http://supercollider.github.io/sc3-plugins/)
  - [msys2](https://www.msys2.org/)
  - [Haskell - ghc](https://www.haskell.org/ghcup/) & [cabal](https://www.haskell.org/cabal/)
  - [SuperDirt](https://github.com/musikinformatik/SuperDirt)
  - [Pulsar-dev Editor](https://pulsar-edit.dev/) with TidalCycles plugin package

---

### トラブルシューティング

もし自動インストールがうまくいかない場合は、以下のドキュメントを参照して手動でインストールしてください。

  - [TidalCyclds \> Installation \> Windows](https://tidalcycles.org/docs/getting-started/windows_install)

---  

### 手動インストール

もし自動インストールがうまくいかない場合は、以下のドキュメントを参照して手動でインストールしてください。

  - [TidalCyclds \> Installation \> Windows\#manual-installation](https://tidalcycles.org/docs/getting-started/windows_install#manual-installation)
