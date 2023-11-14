# FreshLLMs: Refreshing Large Language Models with Search Engine Augmentation
[FreshLLMs: Refreshing Large Language Models with Search Engine Augmentation](https://arxiv.org/abs/2310.03214)

## Memo
- 検索エンジンから取得した関連する最新情報をプロンプトに組み込むことでLLMのパフォーマンスを大幅に向上させる、シンプルな少数ショットプロンプト方法
- １つの質問に対して、OpenAIへのリクエストが１回、SERP_APIへのリクエストが１回必要となる
  - 独自のdemo promptを作成したい場合は、別途SERP_APIの回数は増える（今回のdemo promptを作成するためにはSERP APIへ５回のリクエストが必要）
- Fresh Promptには直接関係しないが興味深い考察
  - OpenAIのモデルが誤った前提の質問に対処するために訓練されている可能性が高い
  - COT(Chain of Thought)は、この論文で対象とする「急速に変化する世界知識を要求する質問や、偽の前提を明らかにする必要がある質問」に対して、精度が悪化することが示された(検証していたモデルはPALMなどでGPT4などの結果はなかった)

## Results
公開されていたコード([freshllms/freshqa](https://github.com/freshllms/freshqa))の一部を日本語用に修正するだけで、正常に動かすことができた。
