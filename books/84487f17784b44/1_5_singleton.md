---
title: "1_5_Singletonパターン"
---

# 「とある村の賢者の栄光と衰退」

![](/images/20230327_gof/In_the_painting_a_wise_figure_stands_atop_a_mountain_ill.png)
*この絵では、一筋の光に照らされた山の上に賢者が立っており、ソフトウェアの世界におけるSingletonパターンのユニークな役割を象徴しています。*

## はじまり
昔々、ある村に、村人の問題を解決するために重要な役割を果たす賢者が住んでいました。彼は知恵と導きの唯一の源であり、シングルトンパターンを体現する存在でした。シングルトンパターンは、クラスが1つのインスタンスしか持たないことを保証し、それへのグローバルなアクセスポイントを提供します。


```python
class WiseMan:
    _instance = None

    @staticmethod
    def get_instance():
        if WiseMan._instance is None:
            WiseMan._instance = WiseMan()
        return WiseMan._instance

    def __init__(self):
        if WiseMan._instance is not None:
            raise Exception("このクラスはシングルトンです！")
        else:
            WiseMan._instance = self

    def solve_problem(self, problem):
        return "賢者の解決策：" + problem
```

## 栄光
その賢者はその知識で有名で、遠く離れた村人たちも彼の助言を求めていた。この場合、シングルトンパターンの強みはそのシンプルさであり、不必要な複雑さを伴わずに誰もが賢者に相談することができるのである。

```python
def main():
    wise_man = WiseMan.get_instance()
    print(wise_man.solve_problem("干ばつ"))

if __name__ == "__main__":
    main()
```

## 新たな挑戦
時が経つにつれ、村は大きくなり、賢者の責任は重くなった。そのため、賢者には常に指導の依頼が殺到し、効率的に職務を遂行することが難しくなった。シングルトンパターンの弱点は、増大する要求を効率的に処理するためのスケールアップができないことであった。

## 衰退
やがて賢者の体調が悪くなり、村人たちは、もはや一人の人間にすべての問題を解決させることはできないと悟った。そこで、村人たちは賢者会議を立ち上げ、責任を分担して解決することにした。

## 新しいアプローチ
村人たちは、増大するニーズにより適した別のデザインパターン(例：「Strategyパターン」「Chain of Responsibilityパターン」等)を採用することにしました。 彼らは評議会を設立し、複数の賢者が協力して指導できるようにしました。

```python
class WiseMan:
    def __init__(self, name):
        self.name = name

    def solve_problem(self, problem):
        return f"{self.name}'s solution to {problem}"

class CouncilOfWiseMen:
    def __init__(self):
        self.wise_men = []

    def add_wise_man(self, wise_man):
self.wise_men.append(wise_man)

def solve_problem(self, problem):
    for wise_man in self.wise_men:
        print(wise_man.solve_problem(problem))
def main():
council = CouncilOfWiseMen()
council.add_wise_man(WiseMan("賢者1"))
council.add_wise_man(WiseMan("賢者2"))
council.add_wise_man(WiseMan("賢者3"))

council.solve_problem("a drought")

if name == "main":
main()
```

## レッスン

村の賢者とシングルトンパターンの話は、デザインパターンは特定の状況では効果的かもしれませんが、状況が変化すると最適な選択ではない可能性があることを教えてくれます。 この場合、村が成長し、賢者への要求が高まるにつれて、シングルトンパターンの限界が明らかになりました。 デザインパターンを実際の問題に適用する際には、デザインパターンのスケーラビリティと適応性を考慮することが不可欠です。