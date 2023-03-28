---
title: "2_1_Adapterパターン"
---

# 「アダプターパターンで調和するジャングル」

![](/images/20230327_gof/A_diverse_group_of_animals_gathers_around_a_water_source.png)
*ジャングルの水源に集まる多様な動物たちが、生命力あふれる水を飲み、分かち合うために調和しています。*
## ジャングルのジレンマ

昔々、うっそうとしたジャングルの中で、さまざまな動物たちが仲良く暮らしていました。動物たちは、それぞれの違いを感じながらも共存し、困ったときには助け合いながら暮らしていました。ある日、ジャングルは干ばつに見舞われ、動物たちは水の分配システムを作ることにしました。

## アダプターパターンが窮地を救う

```python
# 既存インターフェース
class Animal:
    def drink(self, water):
        pass

#  新しいインターフェース
class WaterSource:
    def provide_water(self):
        return "water"

# アダプタークラス
class AnimalWaterAdapter(Animal):
    def __init__(self, water_source):
        self.water_source = water_source

    def drink(self, water):
        return self.water_source.provide_water()

# クライアントコード
def water_distribution(animal: Animal, water):
    animal.drink(water)

# 使用方法
source = WaterSource()
adapter = AnimalWaterAdapter(ソース)
water_distribution(adapter, "water")
```

動物たちは、それぞれの種が独自の方法で水を飲んでいることに気づきました。そこで、それぞれの飲み方を変えずに水を飲める共通のシステムが必要になりました。そこで登場したのが、Adapterパターンです。

Adapterパターンは、互換性のない2つのインターフェースの間のギャップを埋めるのに役立つ構造設計パターンです。ジャングルでは、既存の`Animal`クラスには`drink`メソッドがあり、新しい`WaterSource`クラスには`provide_water`メソッドがありました。動物たちは、既存の飲む動作を変更することなく、水源を利用するためのアダプタを必要としていました。

## アダプターの実装
この問題を解決するために、`Animal`クラスを継承した`AnimalWaterAdapter`クラスを作成しました。このアダプタは、`WaterSource`オブジェクトを引数に取り、`drink`メソッドを実装しました。`drink`メソッドの内部では、`WaterSource`オブジェクトから`provide_water`メソッドを呼び出しています。

## すべての動物に水を配る
動物たちは、`water_distribution`関数を使うことで、動物たち独自の飲み方に関係なく、すべての動物に水を供給できるようになりました。クライアントコードは、水源の根本的な違いや、動物がどのように水を消費するかを意識する必要はありませんでした。アダプタがそれを処理してくれるので、水の分配に集中できるのです。

アダプターのパターンを導入したことで、ジャングルの動物たちは、みんなに効果的に水を配って干ばつを克服することができました。アダプター・パターンが彼らの違いを埋めてくれたおかげで、彼らはより暮らしやすくなり、調和して暮らし続けることができたのです。

## まとめ
この物語では、動物たちがこれまでの行動を変えることなく、新しい配水システムを利用できるようにすることで、アダプターのパターンが力を発揮しています。このパターンがあったからこそ、動物たちは違いを感じながらも共存し続け、共に困難を乗り越えていくことができたのです。