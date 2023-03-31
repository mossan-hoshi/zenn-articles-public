---
title: "3.1 Chain of Responsibilityパターン"
---

# 「ドミノ倒しでつながる小さな動物たちの協力物語」

![](/images/20230327_gof/Disney_Pixar_Style_A_squirrel_bird_and_rabbit_work_toget.jpg)
*リス、鳥、ウサギが息の合ったコンビネーションで、ドミノの列を組んでバリアを作り、その背景には鮮やかな森が広がっています。*


## 始めに
森の中にある小さな村で、ある動物たちがユニークな挑戦をしました。ドミノ倒しの要領で、村に洪水を起こさないようにするのです。動物たちは、それぞれの特技を活かして協力し合いながら、この課題をクリアしていきました。

## 責任の連鎖パターン
```python
class Animal:
    def __init__(self, successor=None):
        self.successor = successor

    def set_successor(self, successor):
        self.successor = successor

    def handle_request(self, request):
        if self.successor:
            self.successor.handle_request(request)
```
## Animalクラス
Animalクラスは、責任の連鎖パターンを表し、各アニマルは固有の役割と後継者を持ちます。ある動物がタスクを完了できない場合、そのリクエストを次の動物に渡します。

```python
class Squirrel(Animal):
    def handle_request(self, request):
        if request == "gather":
            print("Squirrel: I'll gather the dominoes!")
        else:
            super().handle_request(request)

class Bird(Animal):
    def handle_request(self, request):
        if request == "position":
            print("Bird: I'll position the dominoes!")
        else:
            super().handle_request(request)

class Rabbit(Animal):
    def handle_request(self, request):
        if request == "push":
            print("Rabbit: I'll push the dominoes!")
        else:
            super().handle_request(request)

```

## チェインの実装
`Squirrel`、`Bird`、`Rabbit`クラスは、タスクを完了させるために動物がもつ固有の役割を表しています。それぞれの動物が処理できるタスクは決まっており、リクエストを処理できない場合は、後継者に渡します。

```python
squirrel = Squirrel()
bird = Bird()
rabbit = Rabbit()

squirrel.set_successor(bird)
bird.set_successor(rabbit)
```

## チェインの実行
リス（`squirrel`)がきっかけとなり、動物たちが連鎖的につながっていきます。

```python
squirrel.handle_request("gather")
squirrel.handle_request("position")
squirrel.handle_request("push")
```

## タスクを完了させる
森の中心で、動物たちは力を合わせてこの難題を乗り越えました。リスはドミノを集め、鳥はドミノを配置し、ウサギはドミノを押して、洪水から家を守る障壁を作り上げました。

## まとめ
動物たちのチームワークは、責任の連鎖パターンに象徴されるように、協力し合い、独自のスキルを駆使することで、どんな困難も乗り越えられることを示したのです。