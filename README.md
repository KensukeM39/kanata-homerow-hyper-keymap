Editing now...

<h1 align="center">Kanata Homerow Hyper Keymap</h1>

<h3 align="center">
  <img
    alt=""
    title=""
    height=""
    src=""
  />
</h3>

<div align="center">
  text
</div>


## Kanata Home Row Mods + Hyper Keymap

Custom keyboard configuration for [Kanata](https://github.com/jtroo/kanata) focused on comfort and efficiency.  
Supports Home Row Modifiers, Hyper layer, and cross-platform key remapping for macOS & Windows.

🔹 Ideal for: programmers, typists, and keyboard enthusiasts  
🔹 Features: tap-hold, navigation layers, function layers

## Design Philosophy

I created this configuration to reduce hand movement, improve typing ergonomics, and unify behavior across macOS and Windows.

Key ideas:
- Home Row Mods reduce pinky strain
- Hyper Layer enables fast window navigation and shortcuts
- Inspired by QMK and Vim navigation, but works on any keyboard

## Configuration Overview

### Home Row Modifiers (Hold for modifier / Tap for character)
| Key | Hold | Tap |
|-----|------|-----|
| A   | Ctrl | A   |
| S   | Alt  | S   |
| D   | Shift| D   |
| F   | Cmd  | F   |
...

### Layers:
- **Base**: Normal typing
- **Hyper**: Navigation (arrows, page keys, tab switching)
- **Function**: Numpad and shortcuts

## Installation

### macOS
1. Install Kanata: `brew install kanata`
2. Place `kanata.kbd` in `~/.config/kanata/`
3. Run: `kanata --cfg ~/.config/kanata/kanata.kbd`

### Windows
1. Install with `cargo install kanata --features interception_driver`
2. Place config and run:
   ```bash
   kanata.exe --cfg C:\Users\YourName\kanata-windows.kbd

For background execution, see: kanata-tray

## Files

- `kanata.kbd`: Main config (macOS/Linux)
- `kanata-windows.kbd`: Windows config (to be released)
- `README.md`: Setup and philosophy

## References

- [Kanata documentation](https://github.com/jtroo/kanata/blob/main/docs/config.adoc)
- [Kanata sample configs](https://github.com/jtroo/kanata/tree/main/cfg_samples)
- [QMK Firmware](https://qmk.fm/)
- [Keyboard ergonomics](https://wiki.archlinux.org/title/Keyboard_configuration_in_Xorg)

## Learn more

I also wrote an article explaining the design thinking and implementation on Qiita (Japanese):

👉 [カスタムキーボード設定をKanataで実現した話](#)（近日公開予定）
