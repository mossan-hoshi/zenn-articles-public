---
title: "2.2 Bridgeパターン"
---

# 「統一された努力で島の架け橋になる」

![](/images/20230327_gof/A_diverse_group_of_people_from_two_islands_work_together.jpg)
*2つの島の多様な人々が協力し合い、木と石を組み合わせたユニークな橋を巧みに作りながら、川を渡っていく。*

## はじめに

かつてひとつだったふたつの島は、危険な川によって分断されてしまった。両島の住民は、再びつながり、関係を再構築することを切望していたが、橋が必要であった。そこで、橋の設計と実装を分離するために、Bridgeパターンを使用することにした。

## 島をつなぐBridgeパターン

Bridgeパターンを使えば、それぞれの島の資源に応じて、異なる材料や工法で橋を架けることができるようになる。

```python
from abc import ABC, abstractmethod

# アブストラクション ブリッジデザイン
class Bridge(ABC):

    def __init__(self, implementation):
        self.implementation = implementation

    @abstractmethod
    def construct(self):
        pass

# インプリメンテーション 構築技術
class BridgeImplementation(ABC):

    @abstractmethod
    def build(self):
        pass
```

## 2つの島とその橋の物語

A島は木材が豊富で、B島は石材が豊富であった。両島の住民は、木材用と石材用の2つの特化した橋の実装を作ることにした。

```python
# 具体的な実装
class WoodenBridge(BridgeImplementation):

    def build(self):
        return "木造の橋"

class StoneBridge(BridgeImplementation):

    def build(self):
        return "石の橋"
```

## 橋梁工事におけるコラボレーション

コミュニケーションと協力を促進するために、両島の代表者からなる委員会を設立した。委員会は橋のデザインの抽象化として、全体的な構造と外観を定義する一方、建設の詳細は実装に委ねることになった。

```python
# 洗練された抽象性
class IslandBridge(Bridge):

    def construct(self):
        return f"Island bridge made of {self.implementation.build()}"

# ブリッジの実装を作成する
wooden_bridge = WoodenBridge()
stone_bridge = StoneBridge()

# 実装して島橋を作る
bridge_A = IslandBridge(wooden_bridge)
bridge_B = IslandBridge(stone_bridge)
```

## 力を合わせれば、成功する

工事が始まると、2つの島は資源やノウハウを交換し合いながら協力し合った。木の橋はA島から川の真ん中まで、石の橋はB島から真ん中で合流するように建設された。

```python
# 橋を架ける
print(bridge_A.construct()) # 出力されます： 木製の橋でできた島の橋
print(bridge_B.construct()) # 出力されます： 石橋でできた島橋
```

## 結論

最終的にBridgeパターンは、両島の資源と技術の粋を集めた橋の建設を可能にし、両島の再会を実現した。橋の設計の抽象化と実装を切り離すことで、2つの島が再びつながり、調和した生活を送るという夢を実現したのだ。