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

# Workshop 03: TidalCycles Installation Party

---

In this session, we will install TidalCycles, the live coding environment we will mainly use in future workshops.

TidalCycles is a library written in the Haskell programming language, allowing you to represent music with code and perform it in real-time.

Installation can be a bit tricky. Let's proceed step-by-step!

---

## Installation Overview

### Supported OS

- macOS
- Windows
- Linux

---

### Automatic Install vs. Manual Install

There are two methods for installing TidalCycles:

- **Automatic Install**:
  Uses the appropriate package manager for your OS to install all necessary software at once (recommended).
- **Manual Install**:
  Install each piece of software individually. Try this if the automatic installation fails or if you need specific settings.

---

## Installation - MacOS

---

### Automatic Install

Follow these steps to install TidalCycles.

**1. Prerequisite: Install Apple Xcode command line tools**

Open Terminal and run the following command.

```bash
xcode-select --install
````

-----

**2. Run the tidal-bootstrap script**

Run the following command in Terminal.

```bash
curl https://raw.githubusercontent.com/tidalcycles/tidal-bootstrap/master/tidal-bootstrap.command -sSf | sh
```

Installation takes a very long time\! Be patient.

-----

This operation will install the following software:

  - [Haskell Language](https://www.haskell.org/) (Ghcup)
  - [cabal](https://www.haskell.org/cabal/): package system for Haskell and Tidalcycles
  - The Tidal Pattern engine (Tidal Cycles itself)
  - [Pulsar](https://pulsar-edit.dev/): Text editor
      - [tidalcycles plugin](https://github.com/tidalcycles/pulsar-tidalcycles) for Pulsar
  - [SuperCollider](https://supercollider.github.io/) for backend audio generation, and:
      - [SuperDirt](https://github.com/musikinformatik/SuperDirt): sample library used by tidal
      - [sc-3 plugins](https://github.com/supercollider/sc3-plugins): unit generator plugins

-----

### Troubleshooting

If you encounter errors during installation, please refer to the following document for individual solutions.

  - [TidalCyclds \> Installation \> macOS](https://tidalcycles.org/docs/getting-started/macos_install)

-----

### Manual Installation

If the automatic installation does not work, please refer to the following document to install manually.

  - [TidalCyclds \> Installation \> macOS\#manual-installation](https://tidalcycles.org/docs/getting-started/macos_install#manual-installation)

-----

## Installation - Windows

-----

### Automatic Install

**1. Run PowerShell as Administrator**

**2. Install Chocolatey**

Run the following command.

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

-----

**3. Install TidalCycles**

(After installing Chocolatey) Run the following command.

```powershell
choco install tidalcycles
```

Installation takes a very long time\! Be patient.

-----

This operation will install the following software:

  - [git](https://git-scm.com/)
  - [SuperCollider](https://supercollider.github.io/)
  - [sc-3 plugins](http://supercollider.github.io/sc3-plugins/)
  - [msys2](https://www.msys2.org/)
  - [Haskell - ghc](https://www.haskell.org/ghcup/) & [cabal](https://www.haskell.org/cabal/)
  - [SuperDirt](https://github.com/musikinformatik/SuperDirt)
  - [Pulsar-dev Editor](https://pulsar-edit.dev/) with TidalCycles plugin package

-----

### Troubleshooting

If the automatic installation does not work, please refer to the following document to install manually.

  - [TidalCyclds \> Installation \> Windows](https://tidalcycles.org/docs/getting-started/windows_install)

-----

### Manual Installation

If the automatic installation does not work, please refer to the following document to install manually.

  - [TidalCyclds \> Installation \> Windows\#manual-installation](https://www.google.com/search?q=https.org/docs/getting-started/windows_install%23manual-installation)

<!-- end list -->

```
```