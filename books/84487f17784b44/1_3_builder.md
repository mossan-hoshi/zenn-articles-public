---
title: "1.3 Builderパターン"
---

# 「砂漠のオアシスで家を建ている旅人の挑戦」

![](/images/20230327_gof/A_determined_traveler_stands_in_the_warm_glow_of_the_set.jpg)
*夕陽に照らされながら、砂漠のオアシスの風景に溶け込む新築のアドビハウスに見入る旅人*

## 1. 始めに
広大な砂漠の真ん中で、疲れ果てた旅人ジャックがたどり着いたのは、緑豊かなオアシスだった。そのオアシスに家を建ていることにしたジャックだが、砂漠という特殊な環境のため、さまざまな困難に直面する。そこで彼は、ビルダパターンを使って、夢の家を建ていることにした。

## 2. ハウスプランの確立
Jackはまず、砂漠の家に必要な必須コンポーネントの概要を示すHousePlanインタフェースを作成することにした。`HousePlan`インタフェースには、`buildFoundation()`、`buildWalls()`、`buildRoof()`、`buildWindows()`といったメソッドが含まれている。

```python
class HousePlan:
    # ハウスプランのインターフェイス
    def buildFoundation(self): # 基礎の建設
        pass
    def buildWalls(self): # 壁の建設
        pass
    def buildRoof(self): # 屋根の建設
        pass
    def buildWindows(self): # 窓の建設
        pass
```

## 3. ビルダクラスの作成
そして、Jackは、`HousePlan`インタフェースを実装した`AdobeHouseBuilder`と`BrickHouseBuilder`という2つの`Builder`クラスを開発した。それぞれの`Builder`クラスは、特定のタイプの砂漠の家を建設することに特化している。

```python
class AdobeHouseBuilder(HousePlan):
    # アドビハウスの建設方法の実装

class BrickHouseBuilder(HousePlan):
    # レンガ造りの家を作る方法の実装
```

## 4. 住宅を建設する
`Builder`クラスがそろったので、Jackはそれを使って砂漠の家を建ていることができるようになった。彼はまず、建設プロセスの管理を担当する`Director`クラスのインスタンスを作成した。`Director`クラスは`Builder`インスタンスを引数に取り、そのメソッドを用いて特定のタイプに応じた家を建設する。

```python
class Director:
    # ビルダーインスタンスを受け取り、適切なメソッドを呼び出す

    def __init__(self, builder):
        self.builder = builder # ビルダーインスタンスを受け取る

    def construct_house(self):
        # ビルダーインスタンスで適切なメソッドを呼び出す

        self.builder.buildFoundation() # 基礎の建設
        self.builder.buildWalls() # 壁の建設
        self.builder.buildRoof() # 屋根の建設
        self.builder.buildWindows() # 窓の建設
        return self.builder.get_house() # ビルダーインスタンスからハウスを取得する
```


## 5. 適切なビルダを選択する
ジャックは砂漠の環境を評価し、高温乾燥の気候に適しているアドビハウスを建ていることにした。彼は`AdobeHouseBuilder`クラスのインスタンスを作成し、ディレクターに渡す。

```python
adobe_builder = AdobeHouseBuilder() # アドビハウスのビルダーインスタンスを作成
house_director = Director(adobe_builder) # ディレクターインスタンスを作成
```

## 6. ジャックの夢のマイホームを建ている
ジャックは適切なビルダを選択し、ディレクターを設定したことで、いよいよ砂漠のオアシスに夢の家を建ていることができる準備が整った。彼は `house_director` インスタンスで `construct_house()` メソッドを呼び出し、`AdobeHouseBuilder` インスタンスで適切なメソッドを呼び出す。

```python
# ディレクターインスタンスで適切なメソッドを呼び出す
jack_house = house_director.construct_house()
```

## 7. まとめ
JackはBuilderパターンを使って、砂漠のオアシスに夢のマイホームを建ていることに成功した。このデザインパターンによって、彼は、建設プロセスにおける柔軟性とモジュール性を維持しながら、砂漠の環境に特化した家を建設できた。ビルダパターンの活用により、ジャックは複雑なオブジェクトの建設とその表現を分離でき、将来的に追加の家を建設することになった場合、異なる家のタイプや材料に対応することが容易になった。

砂漠に日が沈むころ、ジャックは新しいアドビハウスを誇らしげに眺め、満足げに語った。ビルダパターンのおかげで、彼は砂漠の課題を克服し、オアシスの中心に快適で持続可能な住居を作り上げたのである。