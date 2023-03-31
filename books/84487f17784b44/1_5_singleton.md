---
title: "1.5 Singletonパターン"
---

# 「とある村の賢者の栄光と衰退」

![](/images/20230327_gof/In_the_painting_a_wise_figure_stands_atop_a_mountain_ill.jpg)
*この絵では、一筋の光に照らされた山の上に賢者が立っており、ソフトウェアの世界におけるSingletonパターンのユニークな役割を象徴しています。*

## 始まり
昔々、ある村に、村人の問題を解決するために重要な役割を果たす賢者が住んでいました。彼は知恵と導きの唯一の源であり、シングルトンパターンを体現する存在でした。シングルトンパターンは、クラスが1つのインスタンスしか持たないことを保証し、それへのグローバルなアクセスポイントを提供します。


```python
class WiseMan:
    # 賢者クラス。賢者の名前を受け取る

    _instance = None # 唯一のインスタンスを保持する変数

    @staticmethod
    def get_instance():
        if WiseMan._instance is None:
            WiseMan._instance = WiseMan()　# インスタンスがなければ作成
            # インスタンスがあればそのまま返す(インスタンスが1個だけ存在)
        return WiseMan._instance

    def __init__(self):
        if WiseMan._instance is not None:
            # インスタンスがすでにある場合は例外を発生させる
            raise Exception("このクラスはシングルトンです！")
        else:
            # インスタンスがなければ作成
            WiseMan._instance = self

    def solve_problem(self, problem):
        # 賢者の解決策を返す
        return "賢者の解決策：" + problem
```

## 栄光
その賢者はその知識で有名で、遠く離れた村人たちも彼の助言を求めていた。この場合、シングルトンパターンの強みはそのシンプルさであり、不必要な複雑さを伴わずに誰もが賢者に相談できるのである。

```python
def main():
    wise_man = WiseMan.get_instance() # 賢者のインスタンスを取得
    print(wise_man.solve_problem("干ばつ")) # 問題を解決

if __name__ == "__main__":
    main()
```

## 新たな挑戦
時が経つにつれ、村は大きくなり、賢者の責任は重くなった。そのため、賢者には常に指導の依頼が殺到し、効率的に職務を遂行することが難しくなった。シングルトンパターンの弱点は、増大する要求を効率的に処理するためのスケールアップができないことであった。

## 衰退
やがて賢者の体調が悪くなり、村人たちは、もはや一人の人間にすべての問題を解決させることはできないと悟った。そこで、村人たちは賢者会議を立ち上げ、責任を分担して解決することにした。

## 新しいアプローチ
村人たちは、増大するニーズにより適した別のデザインパターン（例：「Strategyパターン」「Chain of Responsibilityパターン」等）を採用することにしました。 彼らは評議会を設立し、複数の賢者が協力して指導できるようにしました。

:::message alert
一般的にはシングルトンに対する改善策としてはDI(依存性注入）等が使われる模様です。詳しくはt_wadaさんによる解説音声（[その１](https://fukabori.fm/episode/48)、[その２](https://fukabori.fm/episode/49))をお聴きください
:::

```python
class WiseMan:
    # 賢者クラス。賢者の名前を受け取る

    def __init__(self, name):
        self.name = name # 賢者の名前

    def solve_problem(self, problem):
        # 賢者の解決策を返す
        return f"{self.name}'s solution to {problem}"

class CouncilOfWiseMen:
    # 賢者会議クラス。賢者を追加することができる

    def __init__(self):
        self.wise_men = [] # 賢者のリスト

    def add_wise_man(self, wise_man):
        # 賢者を追加する
        self.wise_men.append(wise_man)

def solve_problem(self, problem):
    # 賢者会議の解決策を返す
    for wise_man in self.wise_men: # 賢者のリストをループ
        print(wise_man.solve_problem(problem)) # 賢者の解決策を表示
def main():
    council = CouncilOfWiseMen() # 賢者会議のインスタンスを作成
    council.add_wise_man(WiseMan("賢者1")) # 賢者1を追加
    council.add_wise_man(WiseMan("賢者2")) # 賢者2を追加
    council.add_wise_man(WiseMan("賢者3")) # 賢者3を追加

council.solve_problem("干ばつ") # 賢者会議の解決策を表示

if name == "main":
main()
```


## レッスン

村の賢者とシングルトンパターンの話は、デザインパターンは特定の状況では効果的かもしれませんが、状況が変化すると最適な選択ではない可能性があることを教えてくれます。 この場合、村が成長し、賢者への要求が高まるにつれて、シングルトンパターンの限界が明らかになりました。 デザインパターンを実際の問題に適用する際には、デザインパターンのスケーラビリティと適応性を考慮することが不可欠です。