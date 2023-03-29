---
title: "3.9 Strategyパターン"
---

# 「チェス大会で優勝を目指す少年の戦略的な物語」

![](/images/20230327_gof/In_this_painting_two_young_focused_chess_players_sit_fac.jpg)
*この絵では、集中力のある若い2人のチェスプレーヤーが、机を挟んで手強い相手と向かい合って座り、机に置かれたチェス盤の上に手を置いて次の一手を考えているところを、チェスマスターが傍観している。*

## 少年の夢
昔々、ある小さな町に、ティムという名の少年が住んでいました。ティムは聡明で好奇心旺盛な子供で、チェスに熱中していました。彼の夢は、町が毎年開催するチェス大会で優勝し、チェスチャンピオンの称号を手に入れることでした。

## チェスの達人
ある日、ティムは引退したチェスのグランドマスターである老人に出会い、戦略的なチェスのプレイを教えることに同意した。チェス・マスターはティムに、ゲームのさまざまな状況に合わせて、さまざまな戦略を教えた。彼は、相手の動きを理解し、それに合わせることが、試合に勝つための鍵であると強調した。

## 戦略パターンを応用する
ティムは練習を重ねるうちに、各戦略がPythonのクラスのようであり、チェスの一手がゲームの状態に応じて適用できるメソッドのようであることに気づいたのです。チェスマスターの教えは、異なるアルゴリズムを選択し、相互に適用できる「戦略パターン」に似ていたのです。

```python
from abc import ABC, abstractmethod

class ChessStrategy(ABC):
    @abstractmethod
    def make_move(self):
        pass

class OffensiveStrategy(ChessStrategy):
    def make_move(self):
        return "攻撃的な動き"

class DefensiveStrategy(ChessStrategy):
    def make_move(self):
        return "防御的な動き"

class ChessPlayer:
    def __init__(self, strategy: ChessStrategy):
        self._strategy = strategy

    def set_strategy(self, strategy: ChessStrategy):
        self._strategy = strategy

    def execute_move(self):
        return self._strategy.make_move()
```

## トーナメント開始
大会当日を迎え、ティムのテンションは上がっていく。相手の動きに合わせて攻守を切り替えながら、学んだ戦略を駆使して試合を進めていく。

```python
tim = ChessPlayer(OffensiveStrategy())
print(tim.execute_move())  # 出力されます： 攻撃的な動き

tim.set_strategy(DefensiveStrategy())
print(tim.execute_move())  # 出力されます： 防御的な動き
```

## 最終戦
そしてついに決勝戦、相手は経験豊富で威圧的なディフェンディングチャンピオン。試合が始まると、ティムは攻撃的な戦略でスタートしたが、すぐに相手が防御に長けていることに気がついた。そこで、ティムは守りに徹し、じっくりと隙をうかがうことにした。

## 必勝の一手
ゲームが進むにつれ、Timの相手は過信して決定的なミスを犯し、重要な駒を無防備にしてしまった。その隙にティムは再び攻めに転じ、駒を捕らえ、大きなアドバンテージを得た。最終的にティムは勝利し、チェスチャンピオンになるという夢を実現した。

## 学んだこと
Strategyパターンは、Timの成功に不可欠な役割を果たした。ゲームの状態に応じて適応し、最適な行動を選択することができたからだ。チェストーナメントで優勝を目指すTimの物語は、人生やソフトウェア開発のように、柔軟性と適応性が困難を克服し、目標を達成する鍵であることを思い出させてくれるのです。