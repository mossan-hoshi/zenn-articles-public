---
title: "さらなる学習用資料・この本の作り方・さいごに"
---

# さらなる学習用資料
- 書籍
  - 原典「"Design Patterns: Elements of Reusable Object-Oriented Software"」
    - [原著](https://learning.oreilly.com/library/view/design-patterns-elements/0201633612/) 
    - [日本語訳](https://www.amazon.co.jp/%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E6%8C%87%E5%90%91%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E5%86%8D%E5%88%A9%E7%94%A8%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AE%E3%83%87%E3%82%B6%E3%82%A4%E3%83%B3%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3-%E3%82%A8%E3%83%AA%E3%83%83%E3%82%AF-%E3%82%AC%E3%83%B3%E3%83%9E/dp/4797311126)
  - 「[デザインパターンなのに、エモい。](https://booth.pm/ja/items/1044161)」
  - 「Head Firstデザインパターン第2版」
    - [原著](https://learning.oreilly.com/library/view/head-first-design/9781492077992/)
    - [日本語訳](https://www.oreilly.co.jp/books/9784873119762/)
- Webサイト・記事
  - 「[ちょうぜつ Advent Calendar 2019](https://qiita.com/advent-calendar/2019/memory-chan)」
  - 「[Refactoring guruのDesign Pattern](https://refactoring.guru/design-patterns)」
- ポッドキャスト
  - fukabori.fmでのゲストt_wadaさんによるデザインパターンとDIの解説回（[その１](https://fukabori.fm/episode/48)、[その２](https://fukabori.fm/episode/49)）

# この本の作り方
この本は以下のようなステップで作りました。
- もっとよい方法があったら教えてください（Twitter/プルリク、なんでもよいです）
  - またもっとよい物語や画像ができたらぜひプルリクしてください。まるごと差し替えます
## 作業手順
1. まず各パターンに対してテーマを適当に決めてもらう（ChatGPT）
      - プロンプト
        ```
        GoFデザインパターンの各デザインパターンに対して物語を作ってもらいたいと思いますが、それに先立って各デザインパターンでどのような物語を書くつもりかを1物語30字程度にまとめたうえで羅列してください。なお、似たような物語が存在しないようにジャンルや設定はできるだけ幅を持たせてください。
        ```
        - 今回のときの回答
          ```
          1.2. Factory Method: 宇宙船製造工場でのロボット労働者の冒険
          1.3. Abstract Factory: 魔法のキャンディ王国での製菓家族の物語
          1.4. Builder: 砂漠のオアシスでの家を建てる旅人の挑戦
          1.5. Prototype: クローンを作る未来都市での個性を見つける探求
          1.6. Adapter: ジャングルで異なる動物たちが協力して生きる話
          1.7. Bridge: 分断された2つの島をつなぐ橋を築く住民の奮闘
          1.8. Composite: 雪の森で木々が連携して脅威に立ち向かう物語
          1.9. Decorator: クリスマスツリーの飾りが命を宿す不思議な話
          1.10. Facade: 壁の向こうの秘密の世界への入り口を～～～
          ```

2. 各パターンに対して物語を語ってもらう（ChatGPT）
    効率化のために英語で質問しています。

    - プロンプト（英語。この場合はVisitorパターン。パターン名`'Visitor Pattern'`と1の回答結果を英訳したもの（`'The story of a visitor~`)をプロンプト内に埋め込んでいます）
      ```
      Tell the story of the GoF design pattern 'State Pattern' as a 500-word episode that shows how the design pattern works in the human drama 'The adventures of a superhero whose abilities change with his mood.'. Please set some  commented python code in moderation to make it easy to understand how it works. Please add headings according to the content.The style of writing should match the content of the story.
      ```
      プロンプトの意味（日本語訳）
      ```
      GoFのデザインパターン「State Pattern」が、人間ドラマ「気分で能力が変わるスーパーヒーローの冒険」でどのように機能するかを500字のエピソードとして語ってください。仕組みがわかりやすいように、コメント付きのpythonコードも適度に設定してください。内容に応じて見出しを付けてください。文体はストーリーの内容に合わせてください。
      ```
    - 記事が生成されるのでDeepL等で翻訳してください
      - である・ですます調が混在しがちですので、物語に向いている方に書き直したほうがよいかもしれません

3. 直後の質問で画像生成AI用のプロンプトを作成してもらう（ChatGPT）
      - プロンプト
        ```
        Assuming that a scene from this episode is to be represented as a painting, please provide a short description (one sentence) of the painting. However, please observe the following [Restrictions].

        [Restrictions].
        - Do not include names of people or other proper nouns.
        - Do not mix multiple scenes in the screen.
        - Please start with a general overview and describe the details step by step.
        - Please write in English.
        ```
        意味（日本語訳）
        ```
        このエピソードの1シーンを絵画として表現することを想定し、その絵画の簡単な説明（1文）を記入してください。ただし、以下の【制限事項】をお守りください。

        【制限事項】
        - 人名などの固有名詞を含めないこと。
        - 画面内に複数のシーンを混在させないでください。
        - 全体像から始めて、段階的に詳細を記述してください。
        - 英語で書いてください。
        ```

        - 回答例
          ```
          A powerful superhero, surrounded by a vivid aura representing his shifting emotions, battles menacing villains amidst a chaotic cityscape, with citizens looking on in awe and hope.
          ```

4. 画像生成AIでプロンプトを張り付けて画像を生成する
    - 必要に応じて好みの画像のタイプ（例：`Anime,`）などを指定
    ![](/images/20230327_gof/2023-03-29-15-13-54.png)
    - 具体的なスタイルについては[こちら](https://github.com/willwulfken/MidJourney-Styles-and-Keywords-Reference)等が参考になります。
    - 生成された画像例
      ![](/images/20230327_gof/howto_image_result.jpg)

# さいごに
ChatGPT（GPT-4）とMidjourneyを使っていてこの本のアイデアを思いついてから2日で仕上がりました（作業時間12時間、そのうち半分くらいはChatGPTのエラー解消待ちやMidjourneyプロンプトがうまくいかないことへの対策でした）。これから私もこの本や他のコンテンツでもっとデザインパターンへの理解を深めたいと思います。
従来の「学んでから本を書く」というプロセスから、「**本を書いてもらってから学ぶ**」というSFめいたことが本当にできてしまいました。このデザインパターンに限らずあらゆることの学習に対し適用できるパターンだと感じています。ChatGPTを筆頭とするLLMツールは今後の生活に欠かせないものだと思いますので、まだこの手のツールに慣れていない方には使用し始めることをぜひお勧めして最後の言葉とさせていただきます。
（2023年3月29日）