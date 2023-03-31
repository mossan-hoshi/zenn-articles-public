---
title: "1.4 Prototypeパターン"
---

# 「クローンを作る未来都市での個性を見つける探求」
![](/images/20230327_gof/A_vibrant_cityscape_filled_with_diverse_colorful_charact_df.jpg)
*多様でカラフルなキャラクターが、それぞれの個性を発揮する活気ある街並み。プロトタイプパターンがもたらす新たな創造性と革新性が、彼らの世界を変えています。*
## クローンの近未来都市

誰もがクローンである未来都市で、市民は個性にあこがれていました。その中で、若きアーティスト、アーティは、クローン技術によって誰もが同じような姿や行動をとるようになったにもかかわらず、独自性を表現する方法を見つけ出そうと決意していたのです。

## アーティの発見

ある日、アーティは偶然見付け足古い図書館で、Prototypeパターンを発見しました。このデザインパターンは、既存のオブジェクトをコピーして新しいオブジェクトを作ることができ、元のオブジェクトに影響を与えることなく新しいオブジェクトに変更を加えることができることを知りました。

```python
from copy import deepcopy # ディープコピーを使用するために必要なライブラリ

class Clone:
    # コンストラクタ

    def __init__(self, attributes):
        self.attributes = attributes # オブジェクトの属性を設定する

    def clone(self):
        return deepcopy(self) # オブジェクトをディープコピーする
```

このパターンに触発されたアーティは、ユニークな作品を作るためにアートの実験をすることにしました。

## ユニークな作品を作る

アーティはまず、`Prototype`と呼ばれる基本的な絵画から始めました。そして、`Prototype`のパターンを使って、その絵のコピーを作り、それぞれに少しずつ手を加えていきました。色彩を変えたり、新しい要素を加えたり、構図を変えたり、アーティはそれぞれのコピーに異なる変更を加えていきました。

```python
# ベースオブジェクトを作成する
basic_painting = Clone({"colors": ["red", "blue", "yellow"], "composition": "landscape"})

painting1 = basic_painting.clone() # プロトタイプ・パターンを使用してベースオブジェクトからオブジェクト1を作成する
painting1.attributes["colors"] = ["green", "purple", "orange"] # オブジェクト1の属性を変更する

painting2 = basic_painting.clone() # プロトタイプ・パターンを使用してベースオブジェクトからオブジェクト2を作成する
painting2.attributes["composition"] = "abstract" # オブジェクト2の属性を変更する

painting3 = basic_painting.clone() # プロトタイプ・パターンを使用してベースオブジェクトからオブジェクト3を作成する
painting3.attributes["colors"] = ["cyan", "magenta", "yellow"] # オブジェクト3の属性を変更する
painting3.attributes["composition"] = "portrait" # オブジェクト3の属性を変更する
```

新しい作品の1つ1つが、アーティの創造性のユニークな表現となり、未来都市の市民は注目しました。

## アート革命

アーティのアートが人気を博すにつれ、街の人々も彼の個性的なアプローチに触発されるようになりました。プロトタイプ・パターンを生活のさまざまな場面で活用するようになり、クローンのような単調な生活から脱却していったのです。

ファッションデザイナーは個性的な服を、建築家は個性的な建物を、そしてシェフも斬新な料理を作り始めた。プロトタイプ・パターンは、1つのプロトタイプをもとに、オリジナルに影響を与えることなく、さまざまなユニークなものを作り出すことを可能にしました。

```python
# ファッションデザイナーの衣装オブジェクトを作成する
designer_clothing = Clone({"style": "modern", "materials": ["cotton", "silk"]})

unique_dress = designer_clothing.clone() # 衣装オブジェクトをディープコピーするして、ユニークなドレスオブジェクトを作成する
unique_dress.attributes["style"] = "bohemian" #　ドレスオブジェクトの属性を変更する
 
unique_building = Clone({"architecture": "modern", "materials": ["steel", "glass"]}) #　建築オブジェクトを作成する

green_building = unique_building.clone() #　建築オブジェクトをディープコピーするして、環境に優しい建築オブジェクトを作成する
green_building.attributes["materials"] = ["recycled materials", "solar panels"] #　建築オブジェクトの属性を変更する
```

## 変貌する都市

アーティとプロトタイプ・パターンのおかげで、未来都市は活気に満ちた多様な場所に生まれ変わりました。市民は新しい個性と創造性を受け入れ、街はダイナミックでカラフル、そしてエキサイティングな環境となったのです。


```python
## Prototypeパターンを使用してユニークなオブジェクト1を作成する 
unique_object1 = Clone({"attribute1": "value1", "attribute2": "value2"}) 

# オブジェクトの属性を変更する
unique_object2 = unique_object1.clone() # ユニークなオブジェクト1をディープコピーしてオブジェクト2を作成する
unique_object2.attributes["attribute1"] = "new_value1" # オブジェクト2の属性を変更する
```

街はイノベーションの中心地となり、クローンという出自にとらわれず、一人一人が自分の個性を発揮できるようになりました。人々はもはや自分たちを単なるコピーではなく、自分たちのアイデンティティを持った個人として見ていたのです。

## プロトタイプ・パターンの力

アーティの旅と街の変化は、プロトタイプ・パターンの力を証明するものでした。ひとつのプロトタイプをもとにユニークなオブジェを作ることができるデザインパターンは、街の成長、創造性、個人の表現の可能性を引き出していきました。

アーティがアートを作り続け、人々にインスピレーションを与え続けている間、Prototypeパターンは未来都市の市民にとって希望のシンボルであり続けました。クローンの世界でも、個性と才能を発揮できる場があることを教えてくれたのです。