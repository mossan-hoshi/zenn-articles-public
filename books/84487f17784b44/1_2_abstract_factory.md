---
title: "1.2 Abstract Factoryパターン"
---

# 「魔法のお菓子王国で繰り広げられるお菓子一家の物語」
![](/images/20230327_gof/A_bustling_celebration_scene_in_a_colorful_magical_candy.jpg)

## 始めに
昔々、魔法のお菓子王国では、有名な菓子職人一家が年に一度のお菓子祭りの準備で忙しくしていました。この一族は、お祭りのために最も精巧でおいしいお菓子を作るのが仕事でした。彼らは`AbstractCandyFactory`を使って、ユニークなフレーバーや形をしたさまざまなキャンディーを製造していました。

## 魔法のようなキャンディ工場
`AbstractCandyFactory`は、お菓子の世界ではよく知られたインタフェースで、さまざまなコンクリート工場を実装することで、さまざまなキャンディを作ることができました。最も人気のある2つの具体的な工場は、`ChocolateFactory`と`LollipopFactory`でした。それぞれのコンクリート工場は、特定の種類のお菓子に特化していました。

```python
class AbstractCandyFactory:
    # ファクトリーのインターフェース

    def create_candy(self):
        pass

class ChocolateFactory(AbstractCandyFactory):
    # チョコレートの具象ファクトリー

    def create_candy(self):
        return Chocolate()

class LollipopFactory(AbstractCandyFactory):
    # ロリポップの具象ファクトリー

    def create_candy(self):
        return Lollipop()
```

## お菓子の製造工程
菓子職人一家の最年少メンバーであるLily（リリー）は、お菓子の製造工程に魅了されていました。彼女は、`AbstractCandyFactory`がコンクリート工場と調和して、最もおいしいお菓子を生産していることに驚嘆しました。

それぞれのファクトリは、`create_candy()`というメソッドを持っていて、ファクトリの専門性に応じてユニークなキャンディーオブジェクトを作り出します。たとえば、`ChocolateFactory`は`Chocolate`オブジェクトを作り、`LollipopFactory`は`Lollipop`オブジェクトを作ります。これらのキャンディ・オブジェクトは、ベースとなる`Candy`クラスから派生し、さまざまなキャンディ・タイプの土台となるものでした。

```python
class Candy:
    # お菓子の基底クラス

    def __init__(self, flavor, shape):
        self.flavor = flavor # 味
        self.shape = shape # 形

class Chocolate(Candy):
    # チョコレートの具象クラス

    def __init__(self):
        super().__init__('chocolate', 'bar') # チョコレートの味と形

class Lollipop(Candy):
    # ロリポップの具象クラス

    def __init__(self):
        super().__init__('fruit', 'round') # フルーツの味と形
```

## 大切な日がやってくる
キャンディフェスティバルが近付くと、菓子職人一家は`AbstractCandyFactory`を使ってたくさんのキャンディを作ることに一生懸命になりました。リリーは勉強熱心で、キャンディの生産を管理する仕事を任されました。

彼女は、作るべきキャンディの種類に応じて適切な具象ファクトリを選択し、`create_candy()`メソッドを呼び出すことにしました。こうすることで、家族はそれぞれのキャンディの作成プロセスの複雑な詳細を心配することなく、さまざまな種類のキャンディを効率的に生産できました。

```python
def create_candy_order(abstract_factory):
    # キャンディの注文を作成する
    return abstract_factory.create_candy()

lily_chocolate_factory = ChocolateFactory() # リリーのチョコレート工場
lily_lollipop_factory = LollipopFactory() # リリーのロリポップ工場

chocolate = create_candy_order(lily_chocolate_factory) # チョコレートの注文を作成する
lollipop = create_candy_order(lily_lollipop_factory) # ロリポップの注文を作成する
```

## 成功した祝賀会
キャンディ・フェスティバルは大成功を収め、王国中から人々が集まり、菓子職人一家が作った楽しいお菓子を楽しみました。リリーは、AbstractCandyFactoryとコンクリート工場を見事に管理し、キャンディーの生産をスムーズかつ効率的に行い、皆に満足と驚きを与えました。

`AbstractCandyFactory`は、ファミリーが王国一のキャンディメーカーとしての名声を維持するために、重要な役割を果たしました。キャンディーの種類から製造プロセスを切り離すことで、変化する顧客の要求や好みに無理なく対応できるようになったのです。

## 輝く未来
リリーのお菓子作りへの情熱は、Abstract Factoryのデザインパターンの力を目の当たりにして、ますます強くなっていきました。彼女は、このパターンがあれば、家族のビジネスは何世代にもわたってお菓子の世界で繁栄し、革新し続けることができると思ったのです。

そして、お菓子ファミリーと`AbstractCandyFactory`は、Abstract Factoryデザインパターンの知恵と汎用性に導かれながら、新しい冒険に乗り出し、新しい課題に直面しながら、魔法のお菓子王国に喜びとおいしさを提供し続けたのです。