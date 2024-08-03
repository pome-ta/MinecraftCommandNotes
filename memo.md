# マイクラのコマンド勉強メモ

## 参照しているサイトなど

- [コマンド/execute - Minecraft Wiki](https://minecraft.fandom.com/ja/wiki/%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%89/execute)
- [【役立つ情報】教育版マインクラフトv1.19の新executeコマンド解説＆旧バージョン変換方法 -](https://kidsprogram.co.jp/minecraft/micra_execute)
- [コマンド - Minecraft Japan Wiki](https://minecraftjapan.miraheze.org/wiki/%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%89#execute)

- [アイテム - Minecraft Wiki](https://minecraft.fandom.com/ja/wiki/%E3%82%A2%E3%82%A4%E3%83%86%E3%83%A0)
  - ID を探す用
- [マイクラのアイテムID・ブロックID全1760種一覧！JE/BE対応 ｜ nishiのマイクラ攻略](https://n5v.net/command/block-item-id/)
  - ID 探す用、Java と統合と差分確認

## 雑記メモ内容

- `/execute` は、Java と統合とで、使えるサブコマンドの数に違いがある
  - 使える、使えない。内容に関しては今後調査
- 新execute コマンドは、v1.19 ～

- サブコマンドは、3(4)カテゴリに分けられる
  - 文脈指定
  - ガード
  - (格納先指定)
  - `run`

- `summon` で金床を召喚しようとしたけど、空中はだめっぽい

## 新executeコマンド例

```
# 基本形
だれが、どこで、何を実行？


/extuce as <実行者> at @s run <コマンド>

```


```
# 条件付き
だれが、どこで、特定の場所に、特定のブロックがあった場合、実行

/extuce as <実行者> at @s if block <ブロック座標> <ブロックID> run <コマンド>
```


`'summon' を ブタ として実行できませんでした` と出るのはなんだ？
