# Workshop 03: TidalCycles Install Party

In this session, we will install TidalCycles, the live coding environment we will mainly use in the upcoming workshops. TidalCycles is a library written in the Haskell programming language that allows you to express music with code and perform it in real-time. The installation can be a bit tricky. Let's proceed step-by-step!

## Installation Overview

### Supported OS

- macOS
- Windows
- Linux

### Automatic Installation and Manual Installation

There are two methods for installing TidalCycles:

- Automatic Installation: Uses a package manager appropriate for your OS to install all necessary software at once.
- Manual Installation: Installs each software component individually.

If this is your first time installing, automatic installation is recommended. If you encounter problems with the automatic installation or require specific settings, please try the manual installation.

## Installation - macOS

### Automatic Installation

Follow these steps to install TidalCycles.

1. Preparation: Install Apple Xcode command line tools

    Open Terminal and execute the following command:

    ```bash
    xcode-select --install
    ```

2.  Run the tidal-bootstrap script

    Execute the following command in Terminal:

    ```bash
    curl https://raw.githubusercontent.com/tidalcycles/tidal-bootstrap/master/tidal-bootstrap.command -sSf | sh
    ```

The installation will take a very long time\! Please be patient.

This installs the following components and only installs what is missing. 

- [Haskell Language](https://www.haskell.org/) (Ghcup)
- [cabal](https://www.haskell.org/cabal/): package system for Haskell and Tidalcycles
- The Tidal Pattern engine (Tidal Cycles itself), with the important - BootTidal.hs file
- [Pulsar](https://pulsar-edit.dev/): Text editor
  - [tidalcycles plugin](https://github.com/tidalcycles/pulsar-tidalcycles) for Pulsar
- [SuperCollider](https://supercollider.github.io/) for backend audio generation, and:
  - [SuperDirt](https://github.com/musikinformatik/SuperDirt): sample library used by tidal
  - [sc-3 plugins](https://github.com/supercollider/sc3-plugins): unit generator plugins

### Troubleshooting

If you encounter an error during installation, please refer to the following documentation and address it accordingly.

  - [TidalCyclds \> Installation \> macOS](https://tidalcycles.org/docs/getting-started/macos_install)

### Manual Installation

If the automatic installation fails, please refer to the following documentation to install manually.

  - [TidalCyclds \> Installation \> macOS\#manual-installation](https://tidalcycles.org/docs/getting-started/macos_install#manual-installation)

## Installation - Windows

### Automatic Installation

1.  Run PowerShell as Administrator

2.  Install Chocolatey

    Execute the following command:

    ```powershell
    Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
    ```
    
3.  Install TidalCycles

    Execute the following command:

    ```powershell
    choco install tidalcycles
    ```

The installation will take a very long time\! Please be patient.

This installs the following components and only installs what is missing. 

- [git](https://git-scm.com/)
- [SuperCollider](https://supercollider.github.io/)
- [sc3-plugins](http://supercollider.github.io/sc3-plugins/)
- [msys2](https://www.msys2.org/)
- [Haskell - ghc](https://www.haskell.org/ghcup/) & [cabal](https://www.haskell.org/cabal/)
- [SuperDirt](https://github.com/musikinformatik/SuperDirt) with the [dirt sample library](https://github.com/musikinformatik/Dirt-Samples) and [Vowel quark](https://github.com/supercollider-quarks/Vowel)
- [Pulsar-dev Editor](https://pulsar-edit.dev/) with TidalCycles plugin package

### Troubleshooting

If the automatic installation fails, please refer to the following documentation to install manually.

  - [TidalCyclds \> Installation \> Windows](https://tidalcycles.org/docs/getting-started/windows_install)

### Manual Installation

If the automatic installation fails, please refer to the following documentation to install manually.

  - [TidalCyclds \> Installation \> Windows\#manual-installation](https://tidalcycles.org/docs/getting-started/windows_install#manual-installation)
