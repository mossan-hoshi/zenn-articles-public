---
title: "3_10_Template Methodパターン"
---

# 「料理学校で独自のレシピを発展させる生徒たちの物語」

![](/images/20230327_gof/template.jpg)
*活気ある料理学校の厨房では、若い料理人たちがユニークな形と色彩の料理を作っている。机の片隅にはテンプレートが書かれた紙が置かれている。*

## グランディッシュクッキングスクール

グランディッシュクッキングスクールでは、世界中から生徒が集まり、食欲をそそる料理を作る技術を学びました。この学校の理念は、特定のレシピを教えるのではなく、"テンプレート・メソッド "を用いて、生徒が自分自身の料理の傑作を生み出す力を身につけることでした。

## テンプレート・メソッド

同校の料理長であるグスタボは、生徒たちに「テンプレート・メソッド」という概念を紹介した。彼は、各料理は基本的なアウトラインに従うが、自分の好みに応じて自由にカスタマイズすることができると説明した。

```python
from abc import ABC, abstractmethod

class DishTemplate(ABC):

    def prepare_dish(self):
        self.choose_ingredients()
        self.prepare_ingredients()
        self.cook()
        self.add_final_touches()

    @abstractmethod
    def choose_ingredients(self):
        pass

    @abstractmethod
    def prepare_ingredients(self):
        pass

    @abstractmethod
    def cook(self):
        pass

    @abstractmethod
    def add_final_touches(self):
        pass
```
## 個別レシピの紹介

テンプレートメソッドを手にした学生たちは、自分たちで作った料理の試作を始めた。例えば、Mei(メイ)という学生は、麺つゆを作ることにした。

```python
class MeiNoodleSoup(DishTemplate):

    def choose_ingredients(self):
        print("メイは麺とスープ、そして野菜とスパイスの盛り合わせを選ぶ。")

    def prepare_ingredients(self):
        print("メイは野菜を切り、スパイスを量る。")

    def cook(self):
        print("メイはスープを煮込み、麺を茹でる。")

    def add_final_touches(self):
        print("メイはスープに新鮮なハーブを添えて、蒸し焼きにして提供する。")
```
別の生徒のRaj(ラジ)は、スパイシーなカレー料理を作ることを思いつきました。


```python
class RajCurry(DishTemplate):

    def choose_ingredients(self):
        print("ラジは様々な野菜、スパイス、ココナッツミルクを選びます。")

    def prepare_ingredients(self):
        print("ラージは野菜を切り、スパイスを挽く。")

    def cook(self):
        print("ラジは野菜とスパイスを炒め、ココナッツミルクを加えて煮込む。")

    def add_final_touches(self):
        print("ラジは、カレーをふっくらとしたご飯の上に盛り付ける。")
```
## 料理展の様子

学期が終わると、学校は生徒たちの作品を紹介する料理展を開催しました。メイとラジは、クラスメートとともに、食通の聴衆の前で自分たちの料理を披露しました。

参加者たちは、それぞれが独自の工夫を凝らした多様な料理に驚きました。生徒たちの創造性と、グスタボシェフの「テンプレートメソッド」による指導方法に拍手喝采が送られました。

## まとめ

グランディッシュクッキングスクールの生徒たちは、「テンプレートメソッド」と呼ばれるパターンによって、基本的なアウトラインに沿って、自分の好みに合わせてカスタマイズすることで、自分だけの料理を作ることを学びました。そうすることで、彼らは料理への深い理解を持ち、美食の世界で活躍する熟練したシェフになることができたのです。