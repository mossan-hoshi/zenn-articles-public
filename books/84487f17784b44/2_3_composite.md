---
title: "2_3_Compositeパターン"
---

# 「雪の森のユナイテッドツリー」

![](/images/20230327_gof/A_group_of_trees_interconnected_and_glowing_with_a_myste.png)
*雪景色を背景に、互いにつながり、神秘的なエネルギーを放つ木々が力強く立ち並び、敗れた木こりが背を向ける姿は、結束と協力の力を物語っています。*

## 自然界における複合パターン

雪の降る森では、大きさも種類も違う木々が一緒に暮らしていました。脅威に直面したとき、彼らが一体となって行動できる秘密は、構造設計パターンの一つであるCompositeパターンにありました。Pythonでは、Compositeパターンを使うことで、個々の木や木のグループを一律に扱い、部分と全体の階層を表現することができるようになりました。

```python
from abc import ABC, abstractmethod

class TreeComponent(ABC):
    """
    TreeComponent クラスは、個々のツリーとツリーグループの両方に共通するインターフェイスを定義しています。
    """
    @abstractmethod
    def act(self):
        pass

class Tree(TreeComponent):
    """
    Tree クラスは、TreeComponent インターフェースを実装し、個々の木を表します。
    """
    def __init__(self, tree_type):
        self.tree_type = tree_type

    def act(self):
        return f"{self.tree_type} tree acts."

class TreeGroup(TreeComponent):
    """
    TreeGroup クラスは、TreeComponent インターフェースを実装し、ツリーグループを表します。
    """
    def __init__(self):
        self.trees = []

    def add(self, tree_component):
        self.trees.append(tree_component)

    def remove(self, tree_component):
        self.trees.remove(tree_component)

    def act(self):
        actions = [tree.act() for tree in self.trees]
        return "\n".join(actions)
```

## 脅威のアプローチ

ある日、一人の木こりが森にやってきて、商売のために木を切り倒そうとしました。森はこの脅威に驚き、木々は自分たちの住処を守るために早急に行動を起こさなければならないと考えました。

## 木々は団結する

木はCompositeパターンの力を借りて、木グループを形成して協力することにしました。

```python
# ツリーグループの作成
tree_group_1 = TreeGroup()
tree_group_2 = TreeGroup()
tree_group_3 = TreeGroup()

# ツリーグループに個々のツリーを追加する
tree_group_1.add(Tree("Pine"))
tree_group_1.add(Tree("Oak"))
tree_group_2.add(Tree("Maple"))
tree_group_2.add(Tree("Birch"))
tree_group_3.add(Tree("Spruce"))
tree_group_3.add(Tree("Willow"))

# すべての小さなグループを含む、より大きなツリーグループを作成する。
forest = TreeGroup()
forest.add(tree_group_1)
forest.add(tree_group_2)
forest.add(tree_group_3)
```

## 団結の力

そして、木こりの侵入を阻止するために、木々の力を結集し、作戦を立てました。それぞれの木が独自の能力を発揮し、その力を結集することで、侵入者に対抗する強力な力を生み出したのです。

```python
# 森羅万象が一緒に行動する
print(forest.act())
```

木々が一斉に揺れ、ざわめくと、木こりはますます不安になった。どこからどこまでが木で、どこからどこまでが木なのかがわからなくなり、どの木から切り倒せばいいのかがわからなくなりました。森が一体となり、協調して行動することで、木こりは見事に混乱しました。

## 木こりの退却

森が一体となった姿に圧倒された木こりは、結局、計画を断念することにしました。木々はコンポジットパターンのおかげで、協力し合って自分たちの家を守ることに成功したのです。

```python
# 個々のツリーグループは独立して行動することも可能です。
print(tree_group_1.act())
print(tree_group_2.act())
```

## この物語からの学び
雪の森の木々はその勝利を喜び、コンポジットパターンを採用し続けました。このパターンによって、彼らは効率的にコミュニケーションをとり、一つの組織として行動することができるようになり、また必要に応じて個々のアイデンティティを維持することができるようになったのです。

この話から、Compositeパターンによって、オブジェクトが部分と全体の階層を形成し、個々のコンポーネントとグループの両方を統一的に扱うことができることがわかります。これは、複雑なシステムや構造を扱う場合に特に有効で、操作を簡略化し、異なる要素間のコラボレーションを促進することができます。
