---
title: "3.3 Interpreterパターン"
---

# 「言語を操る魔法使いが世界の謎を解き明かす冒険」

![](/images/20230327_gof/A_young_wizard_surrounded_by_ancient_books_and_scrolls_s.jpg)
*古代の書物や巻物に囲まれた若い魔法使いが、謎の石版を研究し、魔法を使ってシンボルを解読し、隠された知識を明らかにしていきます。*

## 魔法の言葉

魔法生物と未踏の地に満ちた世界で、若き魔法使いエルウィンは、言語を操る隠れた才能を発見します。その才能は、古文書を解読し、魔法生物の言葉を理解することを可能にしました。エルウィンの才能は、世界の謎を解き明かすために不可欠な道具となっていきます。

## インタープリターパターンの動作

魔法言語の研究を深めるエルウィンは、「インタープリター・パターン」を記した書物に出会います。文法規則を表現し、その規則で文章を解釈する方法であることを知ります。そして、インタープリターパターンを使えば、複雑な魔法言語も効率よく解読・理解できることを知ります。

```python
from abc import ABC, abstractmethod

class Expression(ABC):
    @abstractmethod
    def interpret(self, context):
        pass

class TerminalExpression(Expression):
    def __init__(self, value):
        self.value = value

    def interpret(self, context):
        return self.value in context

class OrExpression(Expression):
    def __init__(self, expr1, expr2):
        self.expr1 = expr1
        self.expr2 = expr2

    def interpret(self, context):
        return self.expr1.interpret(context) or self.expr2.interpret(context)

class AndExpression(Expression):
    def __init__(self, expr1, expr2):
        self.expr1 = expr1
        self.expr2 = expr2

    def interpret(self, context):
        return self.expr1.interpret(context) and self.expr2.interpret(context)
```

## 魔法のような出会い

ある日、エルウィンは、未知の魔法言語と思われる記号が刻まれた不思議な石版を見つけました。彼は、この石版を解読するために、インタープリターパターンを適用することを決意します。

```python
# 魔法言語を解釈するための表現を作る
def get_magic_language_expression():
    # 魔法言語ごとに TerminalExpression を作成する
    language1 = TerminalExpression("エレメンタム")
    language2 = TerminalExpression("アルカナム")
    # 2 つの TerminalExpressions の間の
    # ジャンクションとして機能する OrExpression を返す
    return OrExpression(language1, language2)

magic_language = get_magic_language_expression()
```

エルウィンはInterpreterパターンを使って式木を構築し、魔法言語を簡単に解釈することができるようになりました。

```python
# 魔法の言葉を読み解く
context = "エレメンタム, イグニス, アクア ,テラ ,アルカナム ,ヴェントゥス"
result = magic_language.interpret(context)
```

## 解き明かされた秘密

インタープリターパターンのおかげで、エルウィンは石版のメッセージを読み解くことに成功します。すると、そこには魔法の力を増幅させる強力なアーティファクトが隠された宝の在処が記されていた。エルウィンは、言語操作とインタープリターパターンを駆使して、宝物を取り戻す旅に出ます。

エルウィンは世界を探索し、謎を解き明かしながら、インタープリターパターンを使いこなしていきます。新しい言語に出会うたびに、エルウィンは世界の魔法をより深く理解し、言語の力をより深く理解するようになるのです。