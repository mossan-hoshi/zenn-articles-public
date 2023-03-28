---
title: "3_7_Observerパターン"
---

# 「天文台で働く若者が星の動きによるサインを解読する物語」

![](/images/20230327_gof/A_young_astronomer_gazes_at_a_starry_sky_through_a_teles.png)
*若い天文学者が古い天文台の上にある望遠鏡で星空を眺め、その背後では村人が天のお告げのもと、さまざまな行事の準備を進めている。*

## はじめに 天文台と若き天文家たち

ある人里離れた小さな村に、古い天文台で星の動きを観察し、解読するイーサンという青年がいました。彼は天文学に深い情熱を持ち、星には村の未来を変える秘密が隠されていると信じていました。

## オブザーバー・パターンの発見

星を研究しているうちに、イーサンは星の動きを追跡し、解釈するためのもっと効率的な方法が必要だと気づきました。彼は、星と村のさまざまな出来事の間に関係を確立することができるオブザーバーパターンに出くわしたのです。

```python
from abc import ABC, abstractmethod


class StarObserver(ABC):
    @abstractmethod
    def update(self, star_event):
        pass
```

Ethanは、天体の動きを見て解釈するさまざまなオブザーバーの設計図となる、抽象的なStarObserverクラスを作成しました。

## オブザーバーを実装する

イーサンは、3つの主要なイベントを確認した： スターアライメント、コメットサイティング、ルナーエクリプスです。彼は、効率的に解釈するために、それぞれのイベントに対して別々のオブザーバーを作成することにしました。

```python
class StarAlignmentObserver(StarObserver):
    def update(self, star_event):
        if star_event == "StarAlignment":
            print("繁栄と成長を象徴する星の配置を観察")

class CometSightingObserver(StarObserver):
    def update(self, star_event):
        if star_event == "CometSighting":
            print("彗星を目撃、重要な訪問者の到来を示す")

class LunarEclipseObserver(StarObserver):
    def update(self, star_event):
        if star_event == "LunarEclipse":
            print("月食を観測し、今後の課題を警告する")
```
各オブザーバーは、それぞれの天体イベントを処理するための特定のメソッドを持っていました。

## 星を繋ぐ

Ethanは、イベントが発生したときにオブザーバーに通知する方法が必要であることに気づきました。彼は、オブザーバーとその更新を管理するために、StarNotifierクラスを作成しました。

```python
class StarNotifier:
    def __init__(self):
        self.observers = []

    def attach(self, observer):
        self.observers.append(observer)

    def notify(self, star_event):
        for observer in self.observers:
            observer.update(star_event)
```
このクラスは、イーサンが観測者を付けたり外したりして、天体現象が発生したときに通知することができるものでした。

## 啓示が解き明かされる

EthanはStarNotifierにオブザーバーを取り付け始め、やがて天体の出来事を解釈し始めました。

```python
star_notifier = StarNotifier()
star_notifier.attach(StarAlignmentObserver())
star_notifier.attach(CometSightingObserver())
star_notifier.attach(LunarEclipseObserver())

star_notifier.notify("StarAlignment")
star_notifier.notify("CometSighting")
star_notifier.notify("LunarEclipse")
```
観測者たちは、そのサインを読み解きながら、村は来るべき出来事に備えていた。繁栄と成長の知らせに喜び、尊敬する訪問者を歓迎し、前途多難を覚悟する。

## おわりに 星からの知恵

イーサンはオブザーバー・パターンを発見し、星からのサインを効率的に解釈することで、刻々と変化する村の舵取りを支援した。星々の知恵は、村の繁栄、困難、そして新たな出発を導いてくれたのです。