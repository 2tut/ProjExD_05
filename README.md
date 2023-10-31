# ブロック崩し

## 実行環境
- python >= 3.10.9
- pygame >= 2.1.2

## ゲーム概要
- ブロック崩し

## 実装
### 共通基本機能
- [これ](https://algorithm.joho.info/programming/python/pygame-blockout/)

### 担当追加機能
- ブロックからアイテムが出てくる (自分)
- 球が増える (c0a22055)
- バリア
- ブロックを貫通する球
- 何回もたたかないと壊れないブロック
- 爆発するブロック (c0a22091)
- 敵キャラ
    - スコア減る
- ボールがデカくなる/小さくなる (c0b22001)：シフトキーを押した場合にボールのサイズを20*20に変更する。まだ完成体ではなく、scaleの数を具体的に指定せず、変数を用いて自由にサイズの変更ができるようになることが理想
- パドルがデカくなる/小さくなる
- パドルにボールがひっつくようになる
- ミサイル

### メモ
- インデントはスペース4つ
- トップレベルは空行2行、それ以外は空行1行
- クォーテーションはダブルクォーテーション `"` を使う
- イコールを揃えるためにスペースを入れない
- インスタンス内部の変数に直接アクセスせず、なるべくゲッター・セッターメソッドを介す
```
# NG
class Ball():
    ball.speed = 1

if (ball.speed < 2):
    ball.speed = 2

# OK
class Ball():
    ball.speed = 1

    def get_speed(self) -> int:
        return self.speed

    def speed_up(self, int speed):
        self.speed += speed

if (ball.get_speed() < 2):
    ball.speed_up(1)
```

