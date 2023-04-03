---
title: "さらなる学習用資料・この本の作り方・さいごに"
---

# さらなる学習用資料
- 書籍
  - 2〜9章
    - [原著「Fundamentals of Software Architecture」](https://learning.oreilly.com/library/view/design-patterns-elements/0201633612/) 
    - [日本語訳「ソフトウェアアーキテクチャの基礎」](https://www.oreilly.co.jp/books/9784873119823/)
  - 12章「クリーンアーキテクチャ」
    - [原著「Clean Architecture: A Craftsman's Guide to Software Structure and Design」](https://learning.oreilly.com/library/view/clean-architecture-a/9780134494272/) 
    - [日本語訳「Clean Architecture 達人に学ぶソフトウェアの構造と設計」](https://www.kadokawa.co.jp/product/301806000678/)
  - 13章「[オニオンアーキテクチャ](https://jeffreypalermo.com/2008/07/the-onion-architecture-part-1/)」

# この本の作り方
この本は以下のようなステップで作りました。
- もっとよい方法があったら教えてください（Twitter/プルリク、なんでもよいです）
  - またもっとよい物語や画像ができたらぜひプルリクしてください。まるごと差し替えます
## 作業手順
1. まず各アーキテクチャに対してテーマを適当に決めてもらう（ChatGPT）
      - プロンプト（作業効率のため英語にしています。日本語で投稿しても結果には大差はないと思われます）
        ```
        We are thinking of creating contents for beginners of software architecture, in which you can learn about the characteristics, merits and demerits of each architecture through a story that unfolds in the architecture as a building, a town, or a fortress. We are planning to create a different story for each architecture with a different setting, so please start by listing [architecture name], {architecture setting}, and {story outline} for each representative software architecture. Please be as varied as possible in your settings and narrative content.

        [output format].
        - {architecture 1 name}, {architecture 1 configuration}, {architecture 1 narrative summary}.
        - {architecture 2 name}, {architecture 2 configuration}, {architecture 2 narrative summary}.
        ```
        - 今回の回答（翻訳）
          ```
          - モノリシック建築、中世の城、モノリシック:単一の巨大な城が高く、王国のすべての住民と機能を収容しています。その強さとシンプルさは賞賛されていますが、王国が成長するにつれて、城の限界が表面化し始めます。壁に亀裂が生じ、王国は適応と拡大に苦労し、最終的にはより柔軟で分散したアプローチの必要性を認識しています。
          - マイクロサービスアーキテクチャ、島々の群島、グレートアイランドの移動:散在する島々の世界では、各島は1つの機能に特化しており、群島全体のニーズに応えます。これらの島の住民は、バランスを維持するために協力し、コミュニケーションを取り、貿易しなければなりません。このストーリーは、彼らが孤立を克服し、強固なコミュニケーションチャネルを確立し、分散環境で繁栄する彼らの旅をたどります。
          - イベント駆動型アーキテクチャ、忙しい市場、イベン～～～
          ```

2. 各パターンに対して物語を語ってもらう（ChatGPT）

    - プロンプト
      ```
      ソフトウェアアーキテクチャの初心者向けに、建築が建物、都市、要塞であるかのように展開するストーリーを通じて、各アーキテクチャの特徴、長所と短所を学ぶコンテンツを作成する予定です。

      ### [各種情報]
      {アーキテクチャ名}=オニオンアーキテクチャ
      {建築の比喩}=古代寺院
      {タイトル}=悟りの層
      {ストーリーの概要}= 同心円状の部屋があり、各レイヤーが異なるレベルの抽象化を表す古代の寺院は、精神的な旅の中心にあります。レイヤーを移動することにより、主人公は心の安らぎへの道を開始し、依存関係を逆転させ、利益を分離することの重要性を発見します。この体験は、柔軟で保守可能でテスト可能なアーキテクチャの鍵を明らかにします。
      {制約}=[
      「文脈に応じた見出し。」 、
      「ストーリーに適したPythonコードをコメントに含めてください。」 、
      「ストーリーのテキストの量は約1200語である必要があります(特徴、長所と短所を適切に説明できる場合は、1200語より短くすることができます)」、
      「多重度とコメントを含むクラス図の人魚コードが含まれています。」 、
      "ドキュメントの内容がアーキテクチャの特徴、長所、短所を示していることを確認してください。
      ]
      ===

      上記【各種情報】の条件でストーリーをお聞かせください。
      200語を書き終わったら停止し、「続行」と言ったら、停止したポイントの後の次の200語を書き出します(記事全体を出力するまでこの手順を繰り返します)。
      ```
    - 回答例
      ```
      悟りの層
      古代寺院と旅
      昔々、遠い土地に、山の頂上にたたずむ古代の寺院がありました。この寺院は、それぞれが異なるレベルの抽象化に関する知恵と知識を含む、そのユニークな同心円状の部屋で知られていました。神殿の中心には、最も深遠で意味のある概念の核心がありました。

      私たちの物語の主人公、悟りを求める若い旅行者は、この神秘的な場所の話を聞き、そこにたどり着くための挑戦的な旅に乗り出しました。到着すると、彼らは寺院の層を通して彼らを案内し、タマネギ建築の秘密を明らかにする賢明な長老によって迎えられました。～～～
      ```
   - 記事の最後を出力するまで「`続き`」と打って出力させる

3. 直後の質問で画像生成AI用のプロンプトを作成してもらう（ChatGPT)
      - プロンプト
        ```
        Assuming that a scene from this episode is to be represented as a painting, please provide a short description (one sentence) of the painting. However, please observe the following [Restrictions].

        [Restrictions]
        - Write in English.
        - Do not include names of people or other proper nouns.
        - Do not mix multiple scenes in the screen.
        - Start with a general overview and describe the details step by step.
        - Rate each noun and adjective on a 10-point (1-10) metric of "ease of drawing as a picture" and revisit the description until only nouns and adjectives with a score of 9 are included
        ```
        意味（日本語訳）
        ```
        このエピソードの1シーンを絵画として表現することを想定し、その絵画の簡単な説明（1文）を記入してください。ただし、以下の【制限事項】をお守りください。

        【制限事項】
        - 英文で書くこと。
        - 人名などの固有名詞を含めないこと。
        - 画面内に複数のシーンを混在させないこと。
        - 全体像から始めて、細部を段階的に記述する。
        - 各名詞や形容詞を「絵としての描きやすさ」の10段階（1～10）で評価し、9点の名詞や形容詞だけが含まれるまで記述を見直すこと
        ```

        - 回答例
          ```
          A powerful superhero, surrounded by a vivid aura representing his shifting emotions, battles menacing villains amidst a chaotic cityscape, with citizens looking on in awe and hope.
          ```

4. 画像生成AIでプロンプトを張り付けて画像を生成する
    - 必要に応じて好みの画像のタイプ（例：`Anime,`)などを指定
    ![](/images/20230327_gof/2023-03-29-15-13-54.png)
    - 具体的なスタイルについては[こちら](https://github.com/willwulfken/MidJourney-Styles-and-Keywords-Reference)等が参考になります。
    - 生成された画像例
      ![](/images/20230327_gof/howto_image_result.jpg)

# さいごに
ChatGPT（GPT-4）とMidjourneyを使った本第2弾。第1弾「デザインパターンの絵本」（2023年3月29日）から4日（2023年3月4月2日）でリリースできました。
従来の「学んでから本を書く」というプロセスから、「**本を書いてもらってから学ぶ**」というSFめいたことが本当にできてしまいました。このデザインパターンに限らずあらゆることの学習に対し適用できるパターンだと感じています。ChatGPTを筆頭とするLLMツールは今後の生活に欠かせないものだと思いますので、まだこの手のツールに慣れていない方には使用し始めることをぜひお勧めして最後の言葉とさせていただきます。
（2023年3月29日）