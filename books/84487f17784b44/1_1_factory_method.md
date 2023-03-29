---
title: "1.1 Factory Methodパターン"
---

# 「宇宙船工場で働くロボットの冒険」

![](/images/20230327_gof/A_group_of_robots_and_human_engineers_work_harmoniously.jpg)

## 新しいロボットワーカー

遠い惑星にある広大な宇宙船工場で、Robo-1という新しいロボット労働者が生産チームに加わりました。その工場は、さまざまな種類の宇宙船を製造していることで有名で、それぞれにユニークな機能と性能を備えていました。ファクトリーメソッドというパターンを使って、Robo-1はさまざまな宇宙船を簡単に作ることができることを知りました。

## ファクトリーメソッドパターンを理解する
Robo-1が活動を開始すると、貨物船、旅客船、軍艦など、さまざまな宇宙船モデルがあることが確認されました。これらのモデルを作るために、ファクトリーは共通のインターフェースである`SpaceshipCreator`を使い、`create_spaceship()`というメソッドを持っています。このインターフェイスにより、ファクトリーは具体的なクラスを指定することなく、さまざまなタイプの宇宙船を作り出すことができるようになりました。

```python
from abc import ABC, abstractmethod

class SpaceshipCreator(ABC):
    @abstractmethod
    def create_spaceship(self):
        pass
```

Robo-1は、スペースシップのモデルごとに、`SpaceshipCreator`インタフェースを実装した独自のクリエータクラスが存在することに気づきました。これらの具体的なクリエータークラスは、特定のスペースシップインスタンスを作成する役割を担っていました。

```python
class CargoShipCreator(SpaceshipCreator):
    def create_spaceship(self):
        return CargoShip()

class PassengerShipCreator(SpaceshipCreator):
    def create_spaceship(self):
        return PassengerShip()

class MilitaryShipCreator(SpaceshipCreator):
    def create_spaceship(self):
        return MilitaryShip()
```

## 宇宙船を創る

更にRobo-1は、すべての宇宙船モデルが`Spaceship`という共通の基本クラスを共有していることに気づきました。このクラスは、`launch()`や`land()`のように、すべての宇宙船が使う共通のプロパティとメソッドを定義しています。

```python
class Spaceship(ABC):
    @abstractmethod
    def launch(self):
        pass

    @abstractmethod
    def land(self):
        pass
```

各スペースシップモデルには、ベースクラスである`Spaceship`を継承した固有のクラスが存在します。これらのクラスは、各スペースシップ・モデルのユニークな機能と動作を実装しています。

```python
class CargoShip(Spaceship):
    def launch(self):
        print("貨物船発進...")
        
    def land(self):
        print("貨物船着艦...")

class PassengerShip(Spaceship):
    def launch(self):
        print("旅客船発進...")
        
    def land(self):
        print("旅客船着艦...")

class MilitaryShip(Spaceship):
    def launch(self):
        print("軍用船発進...")
        
    def land(self):
        print("軍用船着艦...")
```


## まとめ
ファクトリーメソッドパターンを使うことで、Robo-1は具体的なクラスを知らなくても簡単に新しいスペースシップインスタンスを作ることができます。ファクトリーは、特定のクリエーター・クラスの`create_spaceship()`メソッドを呼び出すだけで、新しいスペース・シップのインスタンスを作成できるのです。
