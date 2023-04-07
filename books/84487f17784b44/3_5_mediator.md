---
title: "3.5 Mediatorパターン"
---

# 「対立する部族が仲介者の力で和解を目指す物語」

![](/images/20230327_gof/high_quality_an_indian_and_a_german_statue_shake_hands_a_a961b34a-e289-4ef8-968b-cfc843dc760e.jpg)
*かつて対立していた2つの部族の指導者の間に立ち、両手を広げ、青空の下で握手を交わし、コミュニケーションによってもたらされた新たな平和と協力の証とする。*

## 戦乱の世 争う部族
かつて、争いの絶えない部族が暮らす世界がありました。部族同士は互いに敵対し、対話もままならない状況でした。しかし、ある日、噂によると、部族を調停する力を持った「仲介者（Mediator)」が現れたと言われています。

## Mediatorパターンの登場
「仲介者」とは、部族のコミュニケーションを管理する存在で、各部族が直接互いにコミュニケーションを取ることなく、仲介者を通じてやりとりを行うことができました。これにより、部族間のコミュニケーションがスムーズになり、争いが次第に減っていきました。

Mediatorパターンは、オブジェクト間のコミュニケーションを仲介するオブジェクトを導入し、オブジェクト間の結合度を低くするデザインパターンです。仲介者は、各オブジェクトの相互作用を集中管理し、オブジェクトが直接相互作用することを避けます。

## Mediatorパターンの特徴と利点
Mediatorパターンの特徴は、オブジェクト間の相互作用を一元管理することで、以下のような利点があります。

- オブジェクト間の結合度を低くし、再利用しやすくする
- オブジェクト間のコミュニケーションを抽象化し、簡単に変更や追加ができる

## Mediatorパターンの欠点
しかし、一方で以下のような欠点も存在します。

- **仲介者が肥大化**しやすく、その結果、保守性が低下することがある

## Mediatorパターンの実装
PythonでMediatorパターンを実装する際に、3つのオブジェクトを持つ例を考えます。まず、抽象クラスを使って仲介者を実装する理由について説明します。抽象クラスを使用することで、仲介者が持つべきメソッドを明示的に定義し、サブクラスで必ず実装されるように強制できます。また、抽象クラスを使用することで、仲介者のインターフェースを一貫させることができます。

以下に、PythonでのMediatorパターンの実装例を示します。

```python
from abc import ABC, abstractmethod

class Mediator(ABC):
    # 仲介者のインターフェースを定義
    @abstractmethod # 抽象メソッド
    def notify(self, sender, event):
        # イベントを発行
        pass

class ConcreteMediator(Mediator):
    def __init__(self):
        self._colleague1 = None
        self._colleague2 = None
        self._colleague3 = None

    def set_colleague1(self, colleague):
        # 部族1を設定
        self._colleague1 = colleague

    def set_colleague2(self, colleague):
        # 部族2を設定
        self._colleague2 = colleague

    def set_colleague3(self, colleague):
        # 部族3を設定
        self._colleague3 = colleague

    def notify(self, sender, event):
        if sender == self._colleague1:
            # 部族1からのイベントを受け取った場合、部族2と部族3にイベントを発行
            self._colleague2.react(event)
            self._colleague3.react(event)
        elif sender == self._colleague2:
            # 部族2からのイベントを受け取った場合、部族1と部族3にイベントを発行
            self._colleague1.react(event)
            self._colleague3.react(event)
        elif sender == self._colleague3:
            # 部族3からのイベントを受け取った場合、部族1と部族2にイベントを発行
            self._colleague1.react(event)
            self._colleague2.react(event)

class Colleague:
    def __init__(self, mediator):
        # 仲介者を設定
        self._mediator = mediator

    def act(self, event):
        # イベントを発行
        self._mediator.notify(self, event)

    def react(self, event):
        # イベントを受け取ったことを表示
        print(f"{self.__class__.__name__} received event: {event}")

# インスタンス生成と設定
mediator = ConcreteMediator() # 仲介者
colleague1 = Colleague(mediator) # 部族1
colleague2 = Colleague(mediator) # 部族2
colleague3 = Colleague(mediator) # 部族3
mediator.set_colleague1(colleague1) # 仲介者に部族1を設定
mediator.set_colleague2(colleague2) # 仲介者に部族2を設定
mediator.set_colleague3(colleague3) # 仲介者に部族3を設定

# イベント発行
colleague1.act("Hello") # 部族1がイベントを発行(仲介者に通知され、仲介者から部族2と部族3に通知される)
```

```mermaid
classDiagram
    Mediator <|-- ConcreteMediator
    Mediator : +notify(sender: object, event: str)
    class ConcreteMediator { 
        -colleague1: Colleague
        -colleague2: Colleague
        -colleague3: Colleague
        +set_colleague1(colleague: Colleague)
        +set_colleague2(colleague: Colleague)
        +set_colleague3(colleague: Colleague)
        +notify(sender: object, event: str)
    }
    class Colleague {
        -mediator: Mediator
        +act(event: str)
        +react(event: str)
    }
    ConcreteMediator --> Colleague
```

このコードでは、Mediator抽象クラスを定義し、具体的な仲介者クラスであるConcreteMediatorを実装しています。また、Colleagueクラスを定義し、3つのオブジェクトが仲介者を介してコミュニケーションを行う様子を示しています。

このように、Mediatorパターンを使うことで、オブジェクト間のコミュニケーションを効果的に管理し、システムの柔軟性と再利用性を向上させることができます。