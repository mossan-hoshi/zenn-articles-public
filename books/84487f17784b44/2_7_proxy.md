---
title: "2_7_Proxyパターン"
---

# 「おとぎ話の世界で他のキャラクターに化ける魔法使いの冒険」

![](/images/20230327_gof/a_diverse_group_of_charact.png)
*騎士、王女、農夫など、さまざまなキャラクターに変身した魔法使いが、魔法のオーラに包まれて佇んでいます。*

## 第1章 魔法的任務
おとぎ話の世界で、賢い魔法使いのエルドリンは、妖精の女王から魔法のような任務を受けました。その仕事とは、さまざまなキャラクターの姿になり、障害を乗り越え、目的を達成するための手助けをすることだったのです。

```python
class Character(ABC):
    @abstractmethod
    def perform_task(self):
        pass

class Wizard(Character):
    def __init__(self, name):
        self.name = name

    def perform_task(self):
        print(f"{self.name}ウィザードが魔法のタスクを実行しています")
```

## 第2章 プロキシウィザード
エルドリンはこの任務を遂行するために、自分が代理人となり、助けようとする人物の姿になることができる呪文を開発しました。この呪文によって、彼は自分のアイデンティティを維持しながら、他の人には困っているキャラクターとして見えるようになりました。

```python
class ProxyWizard(Character):
    def __init__(self, wizard: Wizard, character_type: str):
        self.wizard = wizard
        self.character_type = character_type

    def perform_task(self):
        print(f"{self.wizard.name}ウィザードが {self.character_type} に変身した")
        self.wizard.perform_task()
```

## 第3章 ナイトに変身する
エルドリンが最初に変身したのは、恐ろしいドラゴンを倒す必要のある勇敢な騎士でした。プロキシの呪文を使い、エルドリンは騎士の姿になってドラゴンに立ち向かい、最終的にドラゴンを倒して王国を救いました。

```python
# 魔法使いと騎士の代理人を作る
eldrin = Wizard("Eldrin")
knight_proxy = ProxyWizard(eldrin, "knight")

# エルドリンは騎士に変身して任務を遂行する
knight_proxy.perform_task()
```

## 第4章 プリンセスになる
次にエルドリンは、悪い魔女が守る塔から逃げなければならないお姫様に変身しました。代理の呪文で姫の姿になり、魔女を出し抜いて無事に王国に帰ってきました。

```python
# プリンセスプロキシーを作成する
princess_proxy = ProxyWizard(eldrin, "princess")

# エルドリンは姫に変身して任務を遂行する
princess_proxy.perform_task()
```

## 第5章 最後の変身
エルドリンは最後の仕事として、飢えた王国を養うために魔法の作物を栽培する必要がある謙虚な農夫に変身しました。プロキシスペルで農夫になった彼は、魔法の知識を使って作物を栽培し、人々を飢えから救いました。

```python
# 農家のプロキシを作る
farmer_proxy = ProxyWizard(eldrin, "farmer")

# エルドリンは農夫に変身して任務を遂行する
farmer_proxy.perform_task()
```

## 第6章 報われた報い
すべての任務を終えたエルドリンは、妖精の女王のもとに戻り、その優れた変身能力を褒められました。女王はエルドリンの協力に感謝し、特別な報酬として、代理人なしで自由にどんなキャラクターにも変身できる能力を与えました。

エルドリンは、この新しい力を使って、おとぎ話の世界の住民を助け、平和と繁栄を約束し続けました。

