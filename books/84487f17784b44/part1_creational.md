---
title: "第1部 生成（Creational）についてのパターン"
---

# 第一部 生成（Creational）についてのパターン
Creationalデザインパターンは、オブジェクトの作成プロセスを扱うGoFデザインパターンのカテゴリです。これらのパターンは、インスタンス化プロセスを抽象化し、与えられたユースケースに対してどのオブジェクトを作成する必要があるかを柔軟に決定できます。作成パターンは、オブジェクトの作成がうまく整理され、将来の変更に容易に適応できるようにすることで、コードの再利用性、保守性、および拡張性を促進します。


## アプリ例

| パターン名       | アプリ1            | アプリ2          | アプリ3          | アプリ4          | アプリ5            |
| :--------------- | :----------------- | :--------------- | :--------------- | :--------------- | :----------------- |
| Factory Method   | ログ出力           | 通知システム     | ファイルパーサー | XML解析          | ウィジェット生成   |
| Abstract Factory | グラフ描画         | ウィンドウUI     | データベース接続 | ゲームアセット   | フォント生成       |
| Builder          | SQLクエリ生成      | テキストエディタ | 地図API          | レポート生成     | HTML生成           |
| Prototype        | ゲームオブジェクト | グラフィック図形 | スプレッドシート | ワードプロセッサ | シーン管理         |
| Singleton        | 設定管理           | DB接続           | ロガー           | リソース管理     | プリントスプーラー |



## 1 Factory Method（ファクトリーメソッド） オブジェクトの作成を委ねる
Factory Methodパターンは、スーパークラスでオブジェクトを作成するためのインタフェースを提供する一方、サブクラスで作成されるオブジェクトの種類を変更できるようにする作成デザインパターンです。オブジェクトの生成プロセスをサブクラスに委ねることができ、より柔軟で拡張性の高いコードベースが実現できます。

ファクトリメソッドパターンは、共通のインタフェースをもつオブジェクトを作成する必要がある場合に特に有効ですが、実際の実装や作成プロセスが異なる場合があります。ファクトリメソッドを使用することで、クライアントコードは具体的なクラスの詳細を知る必要がなく、新しいタイプの追加や既存のタイプの変更が容易になります。

- [1 Factory Method「宇宙船工場で働くロボットの冒険」](./1_1_factory_method)

## 2 Abstract Factory（抽象ファクトリー） オブジェクトのファミリーを作成する
抽象ファクトリパターンは、関連または依存するオブジェクトのファミリーを、その具体的なクラスを指定することなく作成する方法を提供する、もう1つの創造的デザインパターンです。オブジェクトのファミリーを作成するためのメソッド群を定義したインタフェースと、それらのメソッドを実装した1つまたは複数の具体的なファクトリクラスで構成されています。

抽象ファクトリパターンは、ファミリーに属するオブジェクトを作成する必要があり、それらの作成にはいくつかの共有ロジックやリソースが必要な場合に有効です。このロジックをファクトリクラスにカプセル化することで、コードがよりモジュール化され、オブジェクトの新しいファミリーを追加したり、既存のファミリーを変更したりすることが容易になります。

- [2 Abstract Factory「魔法のお菓子王国で繰り広げられるお菓子一家の物語」](./1_2_abstract_factory)

## 3 Builder（ビルダー） 構築と表現を切り離す
Builderパターンは、複雑なオブジェクトの構築とその表現を分離することを目的とした創造的デザインパターンです。これは、複雑なオブジェクトを作成するために必要なステップを指定するBuilderインタフェースと、それらのステップを実装する1つまたは複数の具体的なBuilderクラスを導入することによって実現されます。

Builderパターンは、多くのコンポーネントをもつ複雑なオブジェクトを作成する必要がある場合や、作成プロセスが多くのバリエーションをもつ場合に特に有効です。Builderを使用することで、クライアントコードは、構築プロセスの詳細を知らなくても、同じオブジェクトの異なる表現を作成できます。また、より制御されたステップバイステップの構築が可能になり、コードの保守性や理解も容易になります。

- [3 Builder「砂漠のオアシスで家を建てる旅人の挑戦」](./1_3_builder)


## 4 Prototype（プロトタイプ） オブジェクトのクローン化
Prototypeパターンは、既存のオブジェクトをコピーまたはクローンすることによって新しいオブジェクトを作成することを扱う創造的なデザインパターンです。Prototypeパターンは、既存のオブジェクトをコピーして新しいオブジェクトを作成する創造的なデザインパターンであり、自身を複製するためのメソッドを定義したPrototypeインタフェースと、このインタフェースを実装した1つまたは複数の具象クラスを導入することによって実現されます。

Prototypeパターンは、オブジェクトの作成にリソースや時間がかかる場合や、同じオブジェクトのインスタンスを多数作成する必要がある場合に有効です。Prototypeを使用することで、クライアントコードは既存のインスタンスをクローンするだけで新しいオブジェクトを作成でき、ゼロからオブジェクトを作成するコストを避けることができます。また、このパターンでは、クライアントコードに影響を与えることなく、新しいタイプのオブジェクトを追加したり、既存のオブジェクトを変更したりすることが簡単にできます。

- [4 Prototype「クローンを作る未来都市での個性を見つける探求」](./1_4_prototype)

## 5 Singleton（シングルトン） 単一のインスタンスを確保する
Singletonパターンは、クラスが1つのインスタンスしか持たないことを保証し、そのインスタンスへのグローバルなアクセスポイントを提供する創造的なデザインパターンです。クラスのコンストラクタをprivateまたはprotectedにし、そのクラスのユニークなインスタンスを返す静的メソッドを提供することで実現します。

Singletonパターンは、データベース接続、設定オブジェクト、ロギングシステムなど、共有リソースへのアクセスを制御する必要がある場合に有効です。シングルトンを使用することで、クライアントコードはグローバルにアクセス可能な単一のインスタンスを通して共有リソースにアクセスでき、重複や競合がないことを保証します。

結論として、Creational Design Patternsはオブジェクトを作成するためのさまざまなテクニックを提供し、より柔軟で保守的、再利用可能なコードを可能にします。これらのパターンを理解し適用することで、開発者は理解、変更、拡張が容易なソフトウェアシステムを構築できます。

- [5 Singleton「とある村の賢者の物語」](./1_5_singleton)