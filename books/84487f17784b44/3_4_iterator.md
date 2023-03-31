---
title: "3.4 Iteratorパターン"
---

# 「珍しい植物を探すため、園芸家が庭園を巡る物語」

![](/images/20230327_gof/A_horticulturist_carefully_navigates_through_a_lush_gard.jpg)
*園芸家が、希少種への道を照らす魔法の本に導かれながら、鮮やかで多様な植物が生い茂る緑豊かな庭園を慎重に進んでいきます。*


## 始めに

鮮やかな色彩とユニークな植物種に満ちた美しく多様な世界で、情熱的な園芸家の主人公は、国中の庭園に隠された希少な植物を発見する旅に出ます。

## 旅の始まり

園芸家は、珍しい植物を集めるために、さまざまな庭園を探索する旅に出ます。無数の植物が存在する庭園の中で、彼らは魔法の本を使い、順を追って進んでいきます。この本は、園芸家が各植物に順次アクセスできるようにするイテレータの役割を果たします。

```python
class GardenIterator:
    def __init__(self, plants):
        self._plants = plants
        self._current = 0

    def __iter__(self):
        return self

    def __next__(self):
        if self._current >= len(self._plants):
            raise StopIteration
        plant = self._plants[self._current]
        self._current += 1
        return plant
```
## マジカルガーデンズ

それぞれの庭には個性的な植物があり、園芸家はその秘密を解き明らかすためにイテレーターを頼りにしています。イテレータは、各庭園をシームレスに横断し、見落としのないようにできます。

```python
class Garden:
    def __init__(self, plants):
        self._plants = plants

    def __iter__(self):
        return GardenIterator(self._plants)
```
## 希少な植物が明らかに

園芸家が庭園を散策しながら、イテレーターを使って希少価値の高い植物を発掘していきます。魔法の森、神秘的な草原、隠された木立の中を旅していきます。イテレーターの助けを借りて、彼らは行く手にあるユニークな植物をすべて見つけ、記録できるようになりました。


```python
# 使用例
garden = Garden(["Rose", "Lily", "Orchid", "Lotus", "Iris"])
for plant in garden:
    print(plant)
```

## 最後の発見

最後の庭で、園芸家は最も希少な植物、伝説の「ゴールデンブロッサム」を発見します。その植物とは、伝説の「金の花」でした。感動と感謝の気持ちを込めて、園芸家は「金の花」を大切に採取し、冒険を終えました。

## 終わりに
Iteratorパターンの力で、園芸家は広大で多様な植物の世界を見事にナビゲートし、希少な種を発見し、庭園の謎を解き明らかします。この物語では、Iteratorパターンがいかに複雑なトラバースを簡略化し、コレクション内の要素にシームレスにアクセスできるかを示しています。