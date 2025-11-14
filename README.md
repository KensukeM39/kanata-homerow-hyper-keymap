<h1 align="center">Kanata Homerow Hyper Keymap</h1>

<div align="center">
  
  [README (Japanese)](https://github.com/KensukeM39/kanata-homerow-hyper-keymap/README-JP.md)
  
</div>

<h3 align="center">
  <img
    alt=""
    title=""
    height=""
    src=""
  />
</h3>

## Kanata Home Row Mods + Hyper Keymap
Cross-Platform Custom Keyboard Remap for macOS

Custom keyboard configuration for [Kanata](https://github.com/jtroo/kanata) focused on comfort, efficiency, and ergonomic consistency across different keyboard types.

🔹 Ideal for: programmers, typists, and keyboard enthusiasts

🔹 Features: home row modifiers, hyper & function layers, numpad emulation

🔹 Platform: macOS (JIS / US keyboards, both Mac & Windows hardware)

## Motivation

- The CapsLock key, though easily reachable, is rarely used — I wanted to make better use of it.
- I initially tried Karabiner-Elements, but its macOS-only nature made it difficult to reproduce the same behavior across environments.
- Therefore, I chose Kanata, a cross-platform key remapping tool written in Rust, to build a consistent layout usable across macOS setups.

This project provides three configuration files, each tailored to a specific keyboard type used on macOS:

| File                     | Target Keyboard  | Layout | OS    |
| ------------------------ | ---------------- | ------ | ----- |
| `kanata-mac-mac-JIS.kbd` | Apple Keyboard   | JIS    | macOS |
| `kanata-mac-mac-US.kbd`  | Apple Keyboard   | US     | macOS |
| `kanata-mac-win-JIS.kbd` | Windows Keyboard | JIS    | macOS |

## Design Philosophy

This configuration was designed to minimize hand movement and unify modifier behavior between different keyboard layouts.
It enables comfortable typing and seamless workflow switching across devices.

Key ideas:
- Home Row Mods: assign modifiers (Ctrl, Alt, Shift, Cmd) to the home row keys.
  → improves ergonomics and reduces pinky strain.
- Hyper Layer: allows quick navigation (arrows, tab switching, window movement).
- Function Layer: brings back numpad and shortcut functionality even on compact keyboards.
- Inspired by QMK, Vim-style navigation, and Kanata’s simplicity.

## Configuration Overview

### Home Row Modifiers (Hold for modifier / Tap for character)

| Key | Tap | Hold  |
| --- | --- | ----- |
| A   | A   | Left Ctrl   |
| S   | S   | Left Option |
| D   | D   | Left Shift  |
| F   | F   | Left Cmd    |
| J   | J   | Right Cmd   |
| K   | K   | Right Shift |
| L   | L   | Right Option|
| ;   | ;   | Right Ctrl  |

### Layer Structure
```
[Base Layer (+ Home Row Mods)]
  ├── Hyper Layer (Navigation, Home Row Mods)
  └── Function Layer (Navigation, Numpad, Shortcuts)
```
- Base: Normal typing, with home row modifiers
- Hyper: Arrows, Page keys, and tab/window navigation
- Function: Numpad and editor shortcuts for 60% keyboards

### Keymap Images

<details>
  <summary>Base Layer</summary>
    <img width="1287" height="530" alt="macOS-US_base" src="https://github.com/user-attachments/assets/72b7947c-bde7-4dbf-a4ee-bf32fdd8c08f" />
</details>

<details>
  <summary>Hyper Layer (Hold Left capslock)</summary>
    <img width="1287" height="530" alt="macOS-US_hyper" src="https://github.com/user-attachments/assets/74481466-a1c9-499d-9eb1-6c4607aefbbb" />
</details>

<details>
  <summary>Function Layer (Double-tap and hold Left Shift)</summary>
    <img width="1287" height="530" alt="macOS-US_function" src="https://github.com/user-attachments/assets/ce930bb3-f350-436b-a04c-9392cf7fb570" />
</details>

## Installation (macOS)


## Files

| File                     | Description                                   |
| ------------------------ | --------------------------------------------- |
| `kanata-mac-mac-JIS.kbd` | for macOS, Apple JIS keyboard                 |
| `kanata-mac-mac-US.kbd`  | for macOS, Apple US keyboard                  |
| `kanata-mac-win-JIS.kbd` | for macOS, Windows JIS keyboard               |
| `README.md`              | this document (setup, philosophy, references) |

## Respect for the Original Project

This work is built upon the excellent open-source project [Kanata](https://github.com/jtroo/kanata) created by [jtroo](https://github.com/jtroo).
All credit for the underlying system, configuration syntax, and runtime behavior belongs to the Kanata team.

This repository only provides user-level configuration files — no core code has been modified.
I deeply respect the original developers and recommend reading their documentation to understand Kanata’s full capabilities.

> If you find this configuration useful, please consider starring or contributing to the original Kanata repository as well.

## References
- [Kanata](https://github.com/jtroo/kanata) ← main project
- [Kanata Documentation (config.adoc)](https://github.com/jtroo/kanata/blob/main/docs/config.adoc)
- [Kanata Sample Configs](https://github.com/jtroo/kanata/tree/main/cfg_samples)
- [Key List](https://github.com/jtroo/kanata/blob/main/parser/src/keys/mod.rs)
- [JavaScript Key Code Reference](https://www.toptal.com/developers/keycode)
- [Online Keyboard Test Tool](https://www.onlinemictest.com/keyboard-test/)

## Learn More

I’m also writing a Japanese article on Qiita explaining the design process and ergonomic considerations behind this setup.

👉 [カスタムキーボード設定をKanataで実現した話](#)（近日公開予定）

# License

This configuration is distributed under the MIT License.
You are free to use, modify, and share it under proper attribution.
Kanata itself is licensed under LGPL-3.0, which remains applicable to its codebase.
