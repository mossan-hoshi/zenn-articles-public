---
title: "2_5_Facadeパターン"
---

# 「壁の向こうの秘密の世界への入り口を探す子供たちの冒険」

![](/images/20230327_gof/A_group_of_excited_children_stand_in_front_of_a_mysterio.png)
*不思議な壁の前に立つ子どもたちは、目を見開いて驚いています。隠された扉がきらきらと音を立てて開き、その向こうの世界が見えてきます。*

## 謎の壁

むかしむかし、ある小さな村で、子どもたちが、どこまでも続く巨大な壁を見つけました。子どもたちは、その壁の向こうに秘密の世界があるのではないかと興味津々でしたが、その壁はとても頑丈そうで、入り込むことができません。ある日、子どもたちは、隠された入り口があるかどうか、一緒になって探すことにしました。

```python
class MysteriousWall:
    def __init__(self):
        self._hidden_door = HiddenDoor()

    def knock(self):
        self._hidden_door.knock()

    def push(self):
        self._hidden_door.push()

    def pull(self):
        self._hidden_door.pull()

class HiddenDoor:
    def knock(self):
        print("You knocked on the door.")

    def push(self):
        print("You pushed the door.")

    def pull(self):
        print("You pulled the door.")
```

## 公開されたファサード

子どもたちの一人、ルーシーは、壁には複雑な模様がいくつもあり、まるで大きな仕掛けの一部であるかのように見えることに気づきました。そこで、「ファサード」をつくって、もっと簡単に壁とインタラクションできるようにしようと提案しました。

```python
class WallFacade:
    def __init__(self, wall: MysteriousWall):
        self._wall = wall

    def interact_with_wall(self):
        self._wall.knock()
        self._wall.push()
        self._wall.pull()

wall = MysteriousWall()
facade = WallFacade(wall)
```

## 扉が開く

ルーシーは`WallFacade`を使って、壁をノックしたり、押したり、引っ張ったりといろいろな組み合わせを試しました。子どもたちは集まってきて、何かが起こるのを期待しながら待っていました。

```python
def find_secret_combination(facade: WallFacade):
    facade.interact_with_wall()
    facade.interact_with_wall()
    facade.interact_with_wall()

find_secret_combination(facade)
```

## 新しい世界が待っている

何度も試行錯誤の末、ついに秘密の組み合わせが見つかった！壁の向こうには魔法の世界が広がっていたのです。子どもたちは大喜びで、早くこの新しい世界を探検したいと思いました。

## ファサードの力

子どもたちは、Facadeパターンが、`MysteriousWall`のような複雑なシステムとの対話を容易にすることを学びました。シンプルなインターフェースを作ることで、ルーシーとその仲間たちは壁の秘密を解き明かし、まったく新しい冒険の世界を発見することができたのです。

Facadeパターンは、子どもたちにシンプルなインターフェイスを提供しました。そして、複雑な`MysteriousWall`と対話し、最終的に 秘密の扉を見つけることができるようになりました。

こうして子どもたちは、ファサード柄の力を借りて、壁の向こうの隠された世界で数え切れないほどの冒険をすることになったのです。そして、どんな困難も工夫とチームワークで乗り越えられることを、子どもたちはいつも心に留めていました。