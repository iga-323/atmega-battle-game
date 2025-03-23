# DEN-DEN-battler（ATmega328pによる対戦型ゲーム）

## 概要
本プロジェクトは、ATmega328Pを用いて作成した2人対戦型ゲームです。C言語でゲーム制御を行い、直流モータ・LED・スイッチなどの電子部品を活用して、誰でも直感的に遊ぶことのできるゲームにすることを目標に制作しました。
<!-- index.html -->
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>DEN-DEN Battler</title>
</head>
<body>
  <h1>DEN-DEN Battler</h1>
  <p>ATmega328Pを用いて制作した2人対戦型ゲームです。</p>
  <ul>
    <li><a href="assets/how_to_program.pdf">プログラム上の工夫・課題</a></li>
    <li><a href="assets/presentation.pdf">発表スライド</a></li>
    <li><a href="circuit/schematic.jpg">回路図</a></li>
    <li><a href="assets/products.png">装置写真</a></li>
  </ul>
</body>
</html>

## 使用部品
| 部品 | 数量 |
|------|------|
| ATmega328P | 2個 |
| モータードライバ（L298NDC） | 1個 |
| 直流モーター（FE130AV-2270-38-R） | 2個 |
| LED（青・赤） | 各3個 |
| 抵抗（330Ω / 50Ω） | 各6個 |
| タクトスイッチ | 6個 |
| 単三電池 | 4本 |
| ブレッドボード、ジャンパー線、ワニ口クリップ | 各種 |

### デザイン素材
- マスキングテープ（赤・青）
- 色画用紙（赤・青）
- 折り紙（黒）
- 発泡スチロール
- 菓子箱・ダンボール・マグネット など


 ## ゲームルール
- 各プレイヤーにはヘリコプターと３つのHP-LED,そしてUP,Stay,Downの３種類のボタンが用意されている
- 攻撃と守備に分かれており、まず攻撃側がボタンを選択する。
- 押したボタンに応じてそのプレイヤーのヘリコプターのプロペラが以下のように回転する。

UP →	時計回りに回転、　Stay	→　回転しない、　Down	→　反時計回りに回転

- 守備側のプレイヤーは攻撃側のプロペラの動作を見て相手が選択したボタンと同じボタンを3秒以内に選択する。
- 攻守のボタンが一致していれば防御成功となり、一致していなければ防御失敗で守備側のLEDが一つ減るようになっている。
- ゲーム開始時は１ｐが攻撃で２ｐが守備であり、防御成功・失敗判定が行われると攻守交代となる。
- 最終的に相手の３つのLEDを全て消灯させた方が勝利とする。

 
## 使用言語
- C（Atmel Studio）


## フォルダ構成
```
atmega-battle-game/
├── assets/
│   ├── how_to_program.pdf      # プログラム上の工夫・課題
│   ├── presentation.pdf        # 発表スライド
│   └── products.png            # 装置の写真
├── circuit/
│   └── schematic.jpg           # 回路図の画像
├── code/
│   └── main.c                  # ゲーム制御プログラム（C言語）
└── README.md                   # プロジェクト概要
```
