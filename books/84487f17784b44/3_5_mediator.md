---
title: "3.5 Mediatorパターン"
---

# 「対立する部族が仲介者の力で和解を目指す物語」

![](/images/20230327_gof/A_wise_mediator_stands_between_the_leaders_of_two_once-w.jpg)
*かつて対立していた2つの部族の指導者の間に立ち、両手を広げ、青空の下で握手を交わし、コミュニケーションによってもたらされた新たな平和と協力の証とする。*

## 戦国時代の部族

昔々、紛争が絶えない土地で、モンテン族とリベリオン族という2つの部族が戦争をしていた。同じ地域に住んでいながら、共有する資源をどのように管理するかで意見がまとまらなかったのだ。両者の間には敵意が芽生え、混乱と不信を招いていた。

```python
class Montain:
    def send_message(self, message: str):
        pass

class Riverian:
    def send_message(self, message: str):
        pass
```

## 賢明な調停者

最も困難な土地でさえも平和と調和をもたらすことで知られる賢明な調停者(Mediator)が、モンテンとリベリアの対立を耳にした。彼女は介入して、彼らが解決策を見つけるのを助けることにした。

```python
    def __init__(self, montain: Montain, riverian: Riverian):
        self.montain = montain
        self.riverian = riverian

    def relay_message(self, sender, message: str):
        if sender == self.montain:
            self.riverian.send_message(message)
        else:
            self.montain.send_message(message)
```

## 架け橋になる

調停者は両部族の指導者に会い、彼らの不満や懸念に耳を傾けた。調停者は、両部族の指導者に会い、不満や懸念に耳を傾け、悪意なく公平にメッセージを伝えるよう、自分を通してコミュニケーションをとるよう促した。そして、両部族の架け橋となることで、両部族が共通の目標を多く持っていることを認識させたのだ。

```python
class Montain:
    def __init__(self, mediator: Mediator):
        self.mediator = mediator

    def send_message(self, message: str):
        self.mediator.relay_message(self, message)

class Riverian:
    def __init__(self, mediator: Mediator):
        self.mediator = mediator

    def send_message(self, message: str):
        self.mediator.relay_message(self, message)
```
## 新たなはじまり

調停者のたゆまぬ努力により、モンテンとリベラルは共通点を見出すようになった。両者は協力することの利点を理解し、相違点は克服できないものではないことを理解した。そして、調停人の助けを借りて、両者が共有する資源や懸念事項に対応した新しい協定を作り上げた。

```python
montain = Montain()
riverian = Riverian()
mediator = Mediator(montain, riverian)

montain.mediator = mediator
riverian.mediator = mediator

montain.send_message("資源の公平な分配を提案します。")
riverian.send_message("我々は同意する、両部族の繁栄のために協力しよう。")
```
## 平和と繁栄

調停者の助けにより、モンテンとリベリアの人々は対立を過去のものとした。その結果、モンテンとリヴァーリアンは協力し合い、豊かで調和のとれた国土を作り上げた。

調停者の知恵と献身的な努力によって、一度は乱れた国に平和がもたらされ、紛争を解決し、協力を促す調停者のパターンの重要性が示された。