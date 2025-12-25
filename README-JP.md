<h1 align="center">Kanata Homerow Hyper Keymap</h1>

<div align="center">
  
  [README (English)](https://github.com/KensukeM39/kanata-homerow-hyper-keymap/blob/main/README.md)
  
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

[Kanata](https://github.com/jtroo/kanata) というOSSを用いた、macOS向けカスタムキーボード設定になります。

快適さ、効率性、そして異なるキーボード（JIS/US、Mac/Windows）間において人間工学的な一貫性を最重要視して設計しています。

🔹 対象ユーザー：プログラマー、キーボード愛好家など

🔹 機能：Home Row Mods（ホームポジション装飾キー）、独自の Hyper & Function レイヤーなど

🔹 プラットフォーム：macOS（JIS / US 配列, Mac & Windows キーボード両対応）

## 開発動機

- CapsLockキーの有効活用：CapsLockキーは非常に押しやすい位置にあるにも関わらず、ほとんど使われていない。どうにか有効活用したいと考えた。
- クロスプラットフォームへのこだわり：当初はmacOSで定番のKarabiner-Elementsを試したが、macOS専用であるため、異なるOS環境（Windows）での導入が不可能だった。
- Kanataの選択：そこで、クロスプラットフォームで動作するKanataを選択し、macOS上であっても、将来的に他の環境でも再現可能な、一貫したキーレイアウトを構築することに決めた。

このプロジェクトでは、macOS環境で使用される主要なキーボードタイプに合わせた、以下の3つの設定ファイルを作成しました。

| ファイル                     | 対象キーボード | 配列 | OS    |
| ------------------------ | ---------------- | ------ | ----- |
| [`kanata-mac-mac-JIS.kbd`](https://github.com/KensukeM39/kanata-homerow-hyper-keymap/blob/main/kanata-mac-mac-JIS.kbd) | Appleキーボード   | JIS    | macOS |
| [`kanata-mac-mac-US.kbd`](https://github.com/KensukeM39/kanata-homerow-hyper-keymap/blob/main/kanata-mac-mac-US.kbd)  | Appleキーボード   | US     | macOS |
| [`kanata-mac-win-JIS.kbd`](https://github.com/KensukeM39/kanata-homerow-hyper-keymap/blob/main/kanata-mac-win-JIS.kbd) | Windowsキーボード | JIS    | macOS |

## 設計思想

キーマップを考えるにあたって、タイピング中の手の動きを最小限に抑え、異なるキーボードレイアウト間（US/JIS配列）での修飾キーの振る舞いを統一することを目指して設計しました。

アイデア：
- Home Row Mods：修飾キー（Ctrl, Option, Shift, Cmd）をホームポジションのキー（A, S, D, Fなど）に割り当て。
  - 効果：ホームポジションから大きくずらすことなく、操作性の効率化を実現。
- Hyperレイヤー：従来のCapsLockキーを押している間、独自開発したキーマップに切り替える。矢印キー、タブ切り替え、ウィンドウ移動、範囲選択などをホームポジションから手を動かさずに素早く行える。
- Functionレイヤー：Hyperレイヤーの機能（一部）に加えて、コンパクトなキーボードでも、テンキー機能の呼び出しやファンクションキーを押しやすい位置に配置。
- 着想：QMKファームウェアの思想、Vimスタイルのナビゲーション、そしてKanata自体の持つシンプルさから着想を得ています。

## 設定の概要

### Home Row Modifiers (「長押し」で装飾キー / 「タップ」で通常の文字入力)

| キー | タップ時 | 長押し時  |
| --- | --- | ----- |
| A   | A   | Left Ctrl   |
| S   | S   | Left Option |
| D   | D   | Left Shift  |
| F   | F   | Left Cmd    |
| J   | J   | Right Cmd   |
| K   | K   | Right Shift |
| L   | L   | Right Option|
| ;   | ;   | Right Ctrl  |

### レイヤー構造
```
[Baseレイヤー (+ Home Row Mods)]
  ├── Hyperレイヤー (ナビゲーション、Home Row Mods)
  └── Functionレイヤー (ナビゲーション、テンキー、各種ショートカット)
```
- Base：通常のタイピングレイヤー。Home Row Modsが有効。
- Hyper：矢印キー、PageUP/Down、Home/End, タブ/ウィンドウ操作。
- Function：テンキー、および60%キーボードなどで不足しがちなエディタショートカットを配置。

### キーマップのイメージ図

<details>
  <summary>Baseレイヤー</summary>
    <img width="1287" height="530" alt="macOS-US_base" src="https://github.com/user-attachments/assets/72b7947c-bde7-4dbf-a4ee-bf32fdd8c08f" />
</details>

<details>
  <summary>Hyperレイヤー（CapsLockを長押し）</summary>
    <img width="1287" height="530" alt="macOS-US_hyper" src="https://github.com/user-attachments/assets/74481466-a1c9-499d-9eb1-6c4607aefbbb" />
</details>

<details>
  <summary>Functionレイヤー（左Shiftを2回タップして長押し）</summary>
    <img width="1287" height="530" alt="macOS-US_function" src="https://github.com/user-attachments/assets/ce930bb3-f350-436b-a04c-9392cf7fb570" />
</details>

## インストール方法 (macOS)
1. Kanata のインストール（Homebrew を使用してインストールする場合）
```
brew install kanata
```

2. Tearminal を再起動し、Kanata が正常にインストールされたか確認
```
kanata -V
```

## スタートアップ設定 (LaunchCtl)

PC起動時に自動的に Kanata が立ち上がるよう設定します。
[#1537](https://github.com/jtroo/kanata/discussions/1537) を参照してください。

注意点や補足等を記載します。

---

まず、設定ファイル `/Library/LaunchDaemons/com.kanata.launch.plist` を作成します。

<details>
<summary>Vim を使ったファイルの作成方法</summary>

1. 以下のコマンドを実行します。
   ```bash
   sudo vim /Library/LaunchDaemons/com.kanata.launch.plist
   ```  　
2. `i` キーを押して入力モードにします。
3. 下記のXMLコードをコピーして貼り付けます（`<string>/Users/<userID>/...` の部分は自分のユーザー名に書き換えてください）。
4. `Esc` キーを押してコマンドモードに戻ります。
5. `:wq` と入力して Enter を押し、保存して終了します。

</details>

**ファイル内容:**
※ 注意: `<userID>` の部分はご自身のユーザー名（`whoami` コマンドで確認可能）に書き換えてください。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "[http://www.apple.com/DTDs/PropertyList-1.0.dtd](http://www.apple.com/DTDs/PropertyList-1.0.dtd)">
<plist version="1.0">
<dict>
    <key>Label</key>
    <string>com.kanata.launch</string>

    <key>ProgramArguments</key>
    <array>
        <string>/opt/homebrew/bin/kanata</string>
        <string>-c</string>
        <string>/Users/<userID>/.config/kanata/kanata.kbd</string>
        <string>--port</string>
        <string>10000</string>
        <string>--debug</string>
    </array>

    <key>RunAtLoad</key>
    <true/>

    <key>KeepAlive</key>
    <true/>

    <key>StandardOutPath</key>
    <string>/Library/Logs/Kanata/kanata.out.log</string>

    <key>StandardErrorPath</key>
    <string>/Library/Logs/Kanata/kanata.err.log</string>
</dict>
</plist>
```

### サービスの有効化

以下のコマンドを順に実行してサービスを登録・起動します。

```bash
# サービスのロード
sudo launchctl bootstrap system /Library/LaunchDaemons/com.kanata.launch.plist

# サービスの有効化
sudo launchctl enable system/com.kanata.launch

# サービスの開始（またはPC再起動でも可）
sudo launchctl start com.kanata.launch
```

もし上手くいかない場合は、一度 `bootout` してから再度 `bootstrap` を試してください。

```bash
sudo launchctl bootout system /Library/LaunchDaemons/com.kanata.launch.plist

```

## ファイル

| ファイル                     | 説明                                   |
| ------------------------ | --------------------------------------------- |
| [`kanata-mac-mac-JIS.kbd`](https://github.com/KensukeM39/kanata-homerow-hyper-keymap/blob/main/kanata-mac-mac-JIS.kbd) | macOS + Apple JISキーボード用                 |
| [`kanata-mac-mac-US.kbd`](https://github.com/KensukeM39/kanata-homerow-hyper-keymap/blob/main/kanata-mac-mac-US.kbd)  | macOS + Apple USキーボード用                  |
| [`kanata-mac-win-JIS.kbd`](https://github.com/KensukeM39/kanata-homerow-hyper-keymap/blob/main/kanata-mac-win-JIS.kbd) | macOS + Windows JISキーボード用               |
| [`README.md`](https://github.com/KensukeM39/kanata-homerow-hyper-keymap/blob/main/README.md)` | 英語版ドキュメント |
| `README-JP.md`              | 本ドキュメント |


## オリジナルプロジェクトへの敬意

この成果物は、[jtroo](https://github.com/jtroo)氏によって作成された素晴らしいオープンソースプロジェクト [Kanata](https://github.com/jtroo/kanata)  の上に成り立っています。
このリポジトリは、あくまでユーザーレベルの設定ファイルを提供するものであり、Kanataのコアコードは一切変更していません。

オリジナルの開発者に深く敬意を表するとともに、Kanataの全機能を理解するために、ぜひ公式ドキュメントを読むことをお勧めします。

> もしこの設定が役に立ったと感じたら、ぜひオリジナルのKanataリポジトリにもスターを付けたり、Contributeをご検討ください！

## 参考資料
- [Kanata](https://github.com/jtroo/kanata)
- [Kanata ドキュメント (config.adoc)](https://github.com/jtroo/kanata/blob/main/docs/config.adoc)
- [Kanata 設定サンプル集](https://github.com/jtroo/kanata/tree/main/cfg_samples)
- [キーリスト（Kanata内部）](https://github.com/jtroo/kanata/blob/main/parser/src/keys/mod.rs)
- [JavaScript Key Code Reference（キーコードの確認用）](https://www.toptal.com/developers/keycode)
- [Online Keyboard Test Tool（動作確認用）](https://www.onlinemictest.com/keyboard-test/)

## 詳細（Qiita記事）

この設定の設計プロセスや、人間工学的な考慮事項について、Qiitaの方で記事を執筆中です。

👉 [カスタムキーボード設定をKanataで実現した話](#)（近日公開予定）

# ライセンス

この設定ファイル群は、MITライセンスの下で配布されます。 適切な帰属表示（クレジット表記）を行えば、自由に使用、変更、共有することができます。

なお、Kanata本体はLGPL-3.0でライセンスされており、これはKanataのコードベースに引き続き適用されます。
