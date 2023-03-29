---
title: "2.4 Decoratorパターン"
---

# 「クリスマスツリーの飾りが命を宿す不思議な話」

![](/images/20230327_gof/In_a_cozy_living_room_filled_with_the_warmth_of_family_a.jpg)
*家族と愛の温もりに満ちた居心地の良いリビングルームには、美しく飾られたクリスマスツリーがそびえ立ち、枝には鮮やかなオーナメントが飾られ、魔法の天使の見守る中、柔らかで魅惑的な輝きを放ちながら命を吹き込んでいます。*

## オーナメントの魔力覚醒

昔々、ある居心地の良い小さな町で、村人たちは1年で最も不思議な時間を過ごすための準備をしていました。クリスマスです！どの家もきらめく光やリースで家を飾り、もちろんオーナメントで飾られた美しいクリスマスツリーも用意しました。

## 魅惑のオーナメント

ある家では、木の枝に天使のような形をした小さな飾りがぶら下がっていました。この置物は他のものとは違いました。なんと命を吹き込む力を持つ魔法をかけられていたのです！

:::message
pythonにデコレーター機能があるのにそれを使ってないのはいただけないですね。この物語全体を書き直したいと思います🚧🚧
:::

```python
# ベースとなるコンポーネント
class ChristmasTree:
    def decorate(self):
        return "クリスマスツリーは"

# デコレータクラス
class OrnamentDecorator(ChristmasTree):
    def __init__(self, tree: ChristmasTree):
        self.tree = tree

    def decorate(self):
        return f"{self.tree.decorate()} {self.__class__.__name__},"

class AngelOrnament(OrnamentDecorator):
    pass

tree = ChristmasTree()
tree_with_angel = AngelOrnament(tree)
```

## 生命の奇跡

クリスマスイブの夜、天使のオーナメントは突然命を吹き込まれました。天使のオーナメントは、家の中を見回すと、喜びと愛に満ちているのがわかりました。天使は、ツリーの上の他のオーナメントにも幸せをもたらしたいという強い思いを抱きました。

```python
class StarOrnament(OrnamentDecorator):
    pass

class BellOrnament(OrnamentDecorator):
    pass

tree_with_star = StarOrament(tree_with_angel)
tree_with_bell = BellOrnament(tree_with_star)
```

## 魔法を広める

天使のオーナメントは、その魔法の力で他のオーナメントに命を吹き込みました。輝く星、鳴り響く鐘、そしてツリーに飾られた他のユニークな装飾品たち。

```python
class SnowflakeOrnament(OrnamentDecorator):
    pass

tree_with_snowflake = SnowflakeOrnament(tree_with_bell)
```

## ア・ジョイフルセレブレーション

それぞれのオーナメントに命が吹き込まれると、彼らは喜び、クリスマスの精神を祝いました。オーナメントたちはキャロルを歌い、物語を語り、自分たちを取り巻く温もりと愛に驚嘆しました。

```python
def display_tree(tree: ChristmasTree):
    print(tree.decorate())

display_tree(tree_with_snowflake)
```

## それぞれの居場所への回帰

夜が更けるにつれ、オーナメントたちは、クリスマスの朝、家族が目覚める前に元の状態に戻らなければならないことに気づきました。そこで、オーナメントたちはお互いに別れを告げ、魔法を使って元の無機質な飾りに戻りました。

## 思い出に残る

オーナメントは元の状態に戻りましたが、あの特別な夜に共有した魔法は生き続けています。毎年、家族がツリーを飾るとき、オーナメントに命が宿ったあの忘れられないクリスマスイブの温もりと喜びを感じることができたのです。

こうして、魔法のクリスマスツリーのオーナメントの物語は、家族にとって大切な思い出となり、何世代にもわたって語り継がれるようになりました。魔法の天使のオーナメントは、毎年クリスマスイブになると他のオーナメントに命を吹き込み、魔法をかけ続け、愛、喜び、一体感というこの季節の真の精神をみんなに思い出させるのです。

```python
# 魔法は毎年起こる
for year in range(2023, 2030):
    print(f"Year {year}:")
    display_tree(tree_with_snowflake)
    print()
```

これは、クリスマスツリーのオーナメントに命が宿り、他のオーナメントとそれを大切にする家族に幸せと団結をもたらすという魔法の物語で、Decoratorパターンがどのような役割を果たしたかという話です。PythonのコードとDecoratorパターンを使うことで、物語の中で魔法をかけられた天使のオーナメントのように、ツリーに新しいオーナメントを動的に追加し、そのユニークな効果を体験することができたのです。