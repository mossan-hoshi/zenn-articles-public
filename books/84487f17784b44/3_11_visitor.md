---
title: "3.11 Visitorパターン"
---

# 「異次元からの訪問者が地球の文化に触れる物語」

![](/images/20230327_gof/Anime._In_a_warm_and_lively_town_square_a_diverse_group.jpg)
*温かく活気のある町の広場で、音楽家、画家、料理人など多様な人々が、神秘的でありながら親しみやすい人物を囲み、独自の習慣や伝統を共有しながら、活気と調和のある祝賀会を開いています。*

## 来訪者の到着
あるのどかな小さな町に、異次元からの謎の訪問者が現れました。この訪問者は「Voy(ヴォイ)」と呼ばれ、異次元間の理解と友好を目的に、地球の文化や伝統を学ぶことを使命としていました。ヴォイは、異なる習慣や慣習に適応し、環境を破壊しないユニークな能力を持っていたのです。

## 地球人との出会い
ヴォイはまず、さまざまな場所を訪れ、地元の人々と交流し、その習慣や伝統を学ぼうとしました。ヴォイは一人ひとりと関わりながら、その人ならではの知識や経験を訪問者に伝えていきました。

```python
class EarthInhabitant:
    def accept(self, visitor):
        visitor.visit(self)

class VoyVisitor:
    def visit(self, inhabitant):
        pass # 特定の訪問者クラスで実装されること
```

## 異文化を体験する
学習能力の高いヴォイは、出会った人々の習慣をすぐに理解しました。そのため、さまざまな文化的背景を持つ人たちと関係を築くことができました。

```python
class Musician(EarthInhabitant):
    def accept(self, visitor):
        visitor.visit(self)

class Painter(EarthInhabitant):
    def accept(self, visitor):
        visitor.visit(self)

class Chef(EarthInhabitant):
    def accept(self, visitor):
        visitor.visit(self)
```

ボイは旅を続けながら、出会う人ごとにアプローチを変えていき、それぞれの文化のニュアンスを理解することができました。

```python
class MusicVisitor(VoyVisitor):
    def visit(self, musician):
        # ヴォイ learns about music from the musician
        pass

class PaintingVisitor(VoyVisitor):
    def visit(self, painter):
        # ヴォイは画家から絵について学ぶ
        pass

class CookingVisitor(VoyVisitor):
    def visit(self, chef):
        # ヴォイはシェフから料理について学ぶ
        pass
```
## ナレッジの共有
地球の多様な文化について知識を深めたヴォイは、その経験を出会った人たちと共有するようになりました。その結果、互いの背景や伝統をより深く理解し、感謝するようになったのです。

```python
def learn_about_culture(earth_inhabitant, visitor):
    earth_inhabitant.accept(visitor)

musicians = [Musician() for _ in range(3)]
painters = [Painter() for _ in range(3)]
chefs = [Chef() for _ in range(3)]

music_visitor = MusicVisitor()
painting_visitor = PaintingVisitor()
cooking_visitor = CookingVisitor()

for musician in musicians:
    learn_about_culture(musician, music_visitor)

for painter in painters:
    learn_about_culture(painter, painting_visitor)

for chef in chefs:
    learn_about_culture(chef, cooking_visitor)
```

## 調和のとれた結末
ヴォイの旅はやがて終わりを告げたが、彼らが町に与えた影響は計り知れません。ヴォイが出会った人々は、ユニークな訪問者のおかげで、新しい視点と異文化への理解を深めていくことができました。そして、お別れに、町の人たちが集まって、それぞれの才能を発揮し、盛大に祝ったと伝えられています。

ビジターパターンによって、ボイは地球上のさまざまな住民とスムーズに交流し、彼らから学ぶことで、訪問者と出会った人々の双方が互いを理解し、感謝するようになりました。このつながりは、次元を超えた永遠の友情につながったのです。
