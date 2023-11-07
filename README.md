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
- ブロックからアイテムが出てくる ([自分](https://github.com/2tut/ProjExD_05/tree/c0117090/drop-item)) : ブロックを壊すと、一定の確率でアイテムをドロップし、以下のような効果を発揮する
    - ブロックを貫通する球 ([自分](https://github.com/2tut/ProjExD_05/tree/c0117090/bullet-ball)) : しばらくの間、ブロックに当たっても跳ね返らず貫通するようになる
    - 球が増える ([C0A22055](https://github.com/c0a22055/ProjExD_05/tree/C0A22055/more_balls)) : 球が2倍に増える
    - ボールがデカくなる ([C0B22001](https://github.com/c0b2200121/ProjExD_05/tree/C0B22001/ballsize)) : シフトキーを押した場合にボールのサイズを20*20に変更する。まだ完成体ではなく、scaleの数を具体的に指定せず、変数を用いて自由にサイズの変更ができるようになることが理想
- 爆発するブロック ([C0A22055](https://github.com/c0a22055/ProjExD_05/tree/C0A22055/more_balls)) : 赤いブロックにボールが当たった時、爆発エフェクトと同時にその周りのブロックを消す
- 敵キャラ ([C0A22091](https://github.com/c0a22091/ProjExD_05/tree/C0A22091/life)) : 敵キャラが操作するパドルに対して、ビームを撃ってくる。そのビームに触れるとゲームオーバーになる。
    - スコア減る ([C0A22091](https://github.com/c0a22091/ProjExD_05/tree/C0A22091/life)) : 自身が操作しているパドルは二機持っており、玉が二回落ちたらゲームオーバーになる。

### ToDo
- バリア
- 何回もたたかないと壊れないブロック
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

