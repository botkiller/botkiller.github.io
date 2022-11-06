---
layout: page
title: Apple Silicon Video Editing Setup
description: How to configure a new M1 Mac for video editing
img: assets/img/fcpx_m1max.png
importance: 3
category: documentation
---

### Prerequisites 
- Homebrew must be installed.

### Codecs
- Install [Apple Pro Video Formats](https://support.apple.com/kb/DL2050?locale=en_US)
- Install QLVideo (gives thumbnails to MXF and MKV files)
    ```zsh
    brew install --cask qlvideo
    ```

### App Store
- [Final Cut Pro X](https://apps.apple.com/us/app/final-cut-pro/id424389933?mt=12)
- [Motion](https://apps.apple.com/us/app/motion/id434290957?mt=12)
- [Compressor](https://apps.apple.com/us/app/compressor/id424390742?mt=12)

### IINA Media Player
- Download and Install [IINA](https://dl-portal.iina.io/IINA.v1.3.0.dmg)
- `Finder > Get Info > Open With > Change All`
    - Set to IINA.app
- `IINA > Preferences > General`
    - Disable playback history
    - Disable "Open Recent" menu
    - Disable "Play next item automatically" 
    - When media is opened: Pause
    - At Launch: Show open file panel 

### Third Party Software
- Install [Catalyst Browse](https://www.sonycreativesoftware.com/catalystbrowse)
- Install [Adobe CC](https://creativecloud.adobe.com)
- Install [Handbrake](https://handbrake.fr)



