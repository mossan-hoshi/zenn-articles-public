---
title: "はじめに"
---

# 始めに
この本「デザインパターンの絵本」はGoF（Gang of Four）のデザインパターンを絵本を読むように物語ベースで学びたいという思いがきっかけで作り始めました。
これまでに似たようなコンテンツとして「[デザインパターンなのに、エモい。](https://booth.pm/ja/items/1044161)」や「[ちょうぜつ Advent Calendar 2019](https://qiita.com/advent-calendar/2019/memory-chan)」や「[Refactoring guruのDesign Pattern](https://refactoring.guru/design-patterns)」等があり個人的にどちらも非常に好きなコンテンツです。

ただ、すべてのデザインパターンを網羅していなかったり、コードスニペットがなかったり／逆に複雑すぎたりして、個人的にはちょうどよいコンテンツがありませんでした。そこに登場したのがChatGPT（GPT-4）とMidjourneyです。この2つのAIツールの力を借りれば、デザインパターンのコンテンツを自動生成できるのではないかと考えました。そうしてこの本が生まれました。

# この本の対象読者
- デザインパターンを学びたい人
- 一度デザインパターンを学んだんだけどいまいち理解できていない人
- デザインパターンの雰囲気は分かるけど実際どんなコードを書くかわからない人
- Pythonでのデザインパターンの書き方を知りたい人

# 前提条件
- Pythonのコードを読むことができる（詳しい内容はわからなくても雰囲気だけつかめれば大丈夫です）

# 本書の構成
GoFデザインパターン本の3カテゴリ23パターン（後で追加されたパターンについてはまだ対応できていません）それぞれで異なる物語に沿ってデザインパターンを解説します。物語の途中には物語の内容に沿ったPythonコード（詳細な中身は実装されていません）が示され、デザインパターンをどのように実装すればよいかが分かるようになっています。

# 謝辞
この本は、ChatGPT（GPT-4）とMidjourneyの両名のおかげで完成しました。私mossan-hoshiはその手助けをしたにすぎません。本当にありがとうございます。また、一部の画像では新人のBing Image Creatorにも画像を提供いただきました。感謝します。

# 🚨注意事項🚨
- 本書はGPT-4を使って自動生成したものです。さらに私mossan-hoshiはデザインパターンにそんなに詳しくありません。そのため、文章の内容については保証できません（私自身もこれから精読して学んでいこうと思っている段階です）。**もしコードや解説内容に間違いを見付け足場合はお知らせいただけると幸いです。**
  - 本書の原稿は[GitHubのこちらのリポジトリ](https://github.com/mossan-hoshi/zenn-articles-public/tree/main/books/84487f17784b44)で公開されてますので、Pull Requestを送っていただけるとうれしいです。
    - もっとよい物語や画像を作っていただければ物語ごと差し替えたいと思います。参考までに[本書の最後](./closing%252Emd#この本の作り方)にこの本を作るにあたって使用したChatGPTをのプロンプトを載せていますので、同じように物語や画像を作成できます
  - 細かい表記ブレや誤記に関してはそこまで気にしていませんので優先度は低いです
- 画像はMidjourneyを使って自動生成したものです。画像の内容は特定の人物や物体を表しているわけではありません。