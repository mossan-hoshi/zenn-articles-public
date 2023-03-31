---
title: "3.8 Stateパターン"
---

# 「感情によって能力が変わるスーパーヒーローの冒険」

![](/images/20230327_gof/A_powerful_superhero_surrounded_by_a_vivid_aura_represen.jpg)
*感情の移り変わりを表す鮮やかなオーラに包まれたスーパーヒーローが、混沌とした街並みの中で脅威のヴィランと戦い、市民は畏怖と希望を抱いている。*


## 感情の力
スーパーヒーローが正義のために戦う世界で、ひときわ異彩を放つヒーローがいます。そのヒーローは、感情によって力を変えることができるユニークな能力をもっているのです。怒ると驚異的な力を発揮し、冷静になると人を癒し、興奮すると超音速で空を飛ぶことができます。


```python
class HeroState:
    # このメソッドは、ヒーロー状態のベースクラス
    def handle_power(self, hero):
        pass

class AngryState(HeroState):
    # このメソッドは、ヒーローの状態を「パワーステート」に変更する
    def handle_power(self, hero):
        hero.strength = "パワー"

class CalmState(HeroState):
    # このメソッドは、ヒーローの状態を「回復ステート」に変更する
    def handle_power(self, hero):
        hero.healing = "回復"

class ExcitedState(HeroState):
    # このメソッドは、ヒーローの状態を「バランスステート」に変更する
    def handle_power(self, hero):
        hero.speed = "バランス"

class Hero:
    def __init__(self):
        self.state = None

    def set_state(self, state):
        self.state = state

    def change_power(self):
        self.state.handle_power(self)
```

## 困っている街

ある日、街は強力な悪党の集団に襲われる。主人公は、自分の能力を賢く使って窮地を脱しなければならないと考え、行動を開始する。悪党たちが引き起こす破壊を観察しているうちに、彼は怒りを覚え、力を増していく（パワーステート）。

```python
hero = Hero()
hero.set_state(AngryState())
hero.change_power()
print(hero.strength)  # パワー
```

## バランス感覚を養う

戦いが激化するにつれ、主人公は力だけでは悪党を倒せないことに気付く。自分の能力を最大限に発揮するためには、感情のバランスを取る必要がある。そんな中、ふとした瞬間に傷ついた市民を癒し、彼らの信頼を得る（回復ステート）。

```python
hero.set_state(CalmState())
hero.change_power()
print(hero.healing)  # 回復
```

## 最終決戦
街の希望は主人公の手に託され、最後の戦いに挑む。興奮冷めやらぬまま、主人公は大空を駆け巡り、悪党の巣窟を目指します。激しいバトルが繰り広げられる中、主人公は感情を揺さぶりながら、あらゆる力を発揮する（バランスステート）。

```python
hero.set_state(ExcitedState())
hero.change_power()
print(hero.speed)  # バランス
```

## 凱旋とレガシー
感情の力と能力を支配するState(状態/ステート）パターンによって、主人公は悪党を倒し、街を救います。彼の物語は、能力の強さだけでなく、私たちを駆り立てる感情こそが、真の強さであることを思い出させるものである。こうして、変化し続ける力をもつヒーローの遺産は続いていくのです。

このステートパターンは、ヒーローが感情にもとづいてシームレスに能力を切り替えることを可能にし、彼が直面するどんな困難にもダイナミックで適応的な解決策を提供します。