# Java 版 と Bedrock 版 でクロスプレイするサーバー構築

> 2024/08/25

## バージョン等々

### Minecraft

- Launcher
  - v2.2915-1.12.5
- Java 版
  - 1.21.1
- Bedrock 版
  - Windows
    - 1.21.1
  - iOS
    - 1.21.21

### OS

- macOS Sonoma
  - 14.6.1

### Java

anyenv より jenv を使用（意味なかったかも）

- OpenJDK 21.0.4

### サーバー周り

- PaperMC

  - 1.21.1-41.jar

- Geyser-Spigot
  - Build #625 2024/8/23
- floodgate-spigot
  - Build #109 2024/6/14

## 手順

メインどころの参照

[【プラグイン紹介】統合版と Java 版でクロスプレイできるプラグイン【GeyserMC】 - 揚げポテほかほかクラフト](https://agepote.jp/mcplugin/geysermc)

- anyenv で jenv インストール
  - [anyenv を用いて Clean な Mac 開発環境を構築する](https://zenn.dev/duke13/articles/9c74dd595823cbd)
  - [anyenv で jenv をインストールする](https://blog.junpeko.com/blogs/install-jenv-anyenv)
- brew で OpenJDK インストール
  - [【Java】Mac に Homebrew で Java をインストールする #Java - Qiita](https://qiita.com/to3izo/items/aee41c2dd998ce023501)
  - [Mac で多様な Java バージョンとディストリビューションを管理：Homebrew と jEnv の活用 #homebrew - Qiita](https://qiita.com/seijikohara/items/56cc4ac83ef9d686fab2)
- PaperMC 導入
  - 起動中のサーバーは停止
  - [Getting Started | PaperMC Docs](https://docs.papermc.io/paper/getting-started)
    - [Start Script Generator | PaperMC Docs](https://docs.papermc.io/misc/tools/start-script-gen)
      - 初回サーバー起動前に、生成をしディレクトリに格納したが使用せず？
    - 初回起動
      - `java -Xms4G -Xmx4G -jar paper-1.21.1-41.jar --nogui `
        - わらわらとファイル等々が生成させてく
        - 初期設定用の書き換え
    - 通常起動
      - `java -Xms4G -Xmx4G -jar paper-1.21.1-41.jar`
        - GUI 出す感じにしている（深い意味はないけど）
  - Java 版 でサーバーに入ることができる
    - マルチプレイから、IP アドレス
      - 設定の WiFi の詳細より確認
        - `localhost` という書き方だけで可能？（未確認）
- plugin を追加

  - それぞれ、`Spigot/Paper`項目から、`~-Spigot.jar` 取得
    - [Download | GeyserMC](https://geysermc.org/download/?project=geyser)
    - [Download | GeyserMC](https://geysermc.org/download/?project=floodgate)
  - `plugins` ディレクトリ直下に格納
  - サーバーを起動
  - plugin 読み込みログとともに、ディレクトリにもりもりファイルが生成される
  - 諸々設定書き換え

- ポート解放

  - 無線として飛ばすルーターの設定をみてしまっていた
  - メインの方にて、ポート開放
    - LAN 側ホスト
      - どれが適切か不明だったので、サーバーで使った mac の IP を入れた
    - 優先順位があったので、BE 版 -> Java 版 とした

- クロスプレイのワールド
  - mac 側の Java 版は、IP でログイン
  - BE 版は、マルチプレイ画面の LAN にてワールドが表示されていた
  - 表示されないスキンがあった（透明になってた）
