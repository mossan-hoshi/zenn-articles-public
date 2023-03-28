---
title: "第2部 振る舞い（Behavioral）についてのパターン"
---


# 第2部 振る舞い（Behavioral）についてのパターン
ビヘイビアデザインパターンは、オブジェクト間の相互作用を管理するのに役立ち、複雑なシステムの簡素化、メモリ使用の最適化、オブジェクトへのアクセス制御などのソリューションを提供します。これらのパターンを理解し適用することで、より柔軟で保守性の高い、効率的なソフトウェアシステムを実現することができます。

# アダプター 互換性のないインターフェイスを接続する
Adapterパターンは、互換性のない2つのインターフェイスを一緒に使えるようにする構造設計パターンです。これは、ターゲットインターフェイスを実装し、被アダプタクラスへの参照を保持するアダプタクラスを導入することによって実現されます。アダプタクラスは、ターゲットインターフェイスからのメソッド呼び出しを、 アダプタクラスの適切なメソッドに変換する。

アダプタパターンは、互換性のないインタフェースを持つコンポーネントを統合する必要がある場合や、コンポーネントのインタフェースを異なるコンテキストに適合させる必要がある場合に有用です。アダプタを使用することで、クライアントコードは何も変更することなく、ターゲットインターフェイスを通してアダプティーと対話することができ、より高い柔軟性と再利用性を可能にします。

- [2_1_adapter「アダプターパターンで調和するジャングル」](./2_1_adapter%252Emd)

# ブリッジ 抽象化と実装を切り離す
Bridgeパターンは、抽象化と実装を分離し、両者が独立して進化することを可能にする構造設計パターンである。これは、抽象化を表す抽象クラスと実装を表すインターフェイスを導入することで実現されます。抽象クラスは実装インターフェイスへの参照を保持し、メソッドの呼び出しを委譲する。

Bridgeパターンは、複雑なクラス階層を、抽象化用と実装用の2つの直交する階層に分離する必要がある場合に有効です。Bridgeを使用することで、クライアントコードは実装の詳細を気にすることなく抽象化を使用することができ、より柔軟で保守性の高いコードを実現することができます。

- [2_2_bridge「統一された努力で島の架け橋になる」](./2_2_bridge%252Emd)

# コンポジット オブジェクトをツリー構造として扱う
Compositeパターンは、オブジェクトを木構造に構成し、個々のオブジェクトと構成を統一的に扱えるようにする構造設計パターンである。親子関係を管理するメソッドを持つComponentインタフェースと、このインタフェースを実装する1つ以上の具象クラスを導入することで実現する。

Compositeパターンは、部分と全体の階層を表現する必要がある場合や、クライアントコードが個々のオブジェクトとそのコンポジションを一貫した方法で扱う必要がある場合に有用である。Compositeを使用することで、クライアントコードは、個々のオブジェクトとその構成を区別することなく、ツリー構造内のオブジェクトと対話することができ、コードを簡素化し、保守性を向上させることができます。

- [2_3_composite「雪の森のユナイテッドツリー」](./2_3_composite%252Emd)

# デコレーター： 追加の責任でオブジェクトを強化する
Decoratorパターンは、オブジェクトの既存の動作に影響を与えることなく、追加の責任で動的に拡張することを可能にする構造設計パターンです。これは、装飾するオブジェクトと同じインタフェースを実装し、そのオブジェクトへの参照を保持するDecoratorクラスを導入することによって実現されます。デコレータークラスは、インターフェースのメソッドをオーバーライドし、その呼び出しをデコレートされたオブジェクトに委譲し、必要に応じて動作を追加・変更します。

Decoratorパターンは、継承を行わずにオブジェクトの機能を拡張する必要がある場合や、オブジェクトに "Decorator "を追加する必要がある場合に有効です。Decoratorを使用することで、クライアントコードはオブジェクトに新しい機能を持たせることができ、その機能は維持されます。を、より柔軟で再利用可能なコードに変更することができます。

- [2_4_decorator「クリスマスツリーの飾りが命を宿す不思議な話」](./2_4_decorator%252Emd)

# ファサード 複雑なサブシステムを簡素化する
Facadeパターンは、複雑なサブシステムに簡素化されたインターフェースを提供する動作設計パターンである。これは、Facadeクラスを導入することで実現され、サブシステムを使いやすくするための上位レベルのインターフェイスとして機能する。Facadeクラスはサブシステムの複雑さをカプセル化し、クライアントコードが単一の簡素化されたインターフェイスを通してサブシステムと対話することを可能にします。

Facadeパターンは、多くのコンポーネントや複雑な依存関係を持つ大規模なシステムやライブラリを扱う場合に、特に有用です。Facadeを使用することで、クライアントコードはサブシステムの複雑性から遮断され、理解や保守が容易になります。さらに、Facadeはサブシステムをクライアントコードから切り離すのに役立ち、システムの柔軟性と再利用性を向上させることができる。

- [2_5_facade「壁の向こうの秘密の世界への入り口を探す子供たちの冒険」](./2_5_facade%252Emd)

# フライウェイト メモリフットプリントを削減する
Flyweightパターンは、複数のインスタンス間で共通部分を共有することで、オブジェクトのメモリ使用量を最小化することを目的とした動作設計パターンである。これは、共有オブジェクトの共通メソッドを定義したFlyweightインターフェイスと、このインターフェイスを実装した1つまたは複数の具体的なFlyweightクラスを導入することによって実現されます。共有オブジェクトはFlyweight Factoryによって管理され、固有のFlyweightのインスタンスが1つだけ作成されるようにします。

Flyweightパターンは、ゲームのグラフィック要素やドキュメントエディターのテキスト文字など、似たような特性を持つオブジェクトを大量に作成する必要がある場合に特に有効です。Flyweightを使用することで、メモリ使用量を大幅に削減することができ、パフォーマンスとスケーラビリティの向上につながる。

- [2_6_flyweight「蜂の巣で働くハチたちが効率よく花の蜜を集める物語」](./2_6_flyweight%252Emd)

# プロキシ オブジェクトへのアクセスを制御する
Proxyパターンは、別のオブジェクトの代用オブジェクトやプレースホルダーを提供し、元のオブジェクトへのアクセスを制御する動作設計パターンである。これは、元のオブジェクトと同じインターフェイスを持つProxyクラスと、元のオブジェクトへの参照を導入することで実現されます。Proxyクラスは、元のオブジェクトへのすべての呼び出しを傍受し、呼び出しを転送する前または後に追加のアクションを実行できるようにします。

Proxyパターンは、セキュリティチェック、ロギング、キャッシュの提供など、さまざまなシナリオで役立ちます。Proxyを使用することで、クライアントコードは実行される追加アクションを意識することなく元のオブジェクトと対話することができ、よりモジュール化された保守性の高いシステムを実現できます。

- [2_7_proxy「おとぎ話の世界で他のキャラクターに化ける魔法使いの冒険」](./2_7_proxy%252Emd)