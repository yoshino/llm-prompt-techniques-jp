# Rephrase and Respond: Let Large Language Models Ask Better Questions for Themselves
[Rephrase and Respond: Let Large Language Models Ask Better Questions for Themselves](https://arxiv.org/abs/2311.04205)

## Memo
- 本研究では、LLMも自らの考えの枠を持っていると仮定し、人間とLLMの間で使用される枠に差異があることは珍しくないと観察しています。
- この問題に対処するために、LLMに質問を言い換えさせ、よりよい回答のために追加の詳細を組み込ませることを提案します。私たちの観察によると、人間によって投げかけられた質問とは対照的に、言い換えられた質問は意味の明確さを高め、固有の曖昧性を解消するのに役立つ傾向があります。
- 特に、Two-step RaRは、より能力のあるLLMからの言い換えた質問を、より初期のモデルに対する曖昧さを明確にするために移行させるのを促進します。
- RaRはCoTに補完的であり、実験結果によって確認されたように、改善のために簡単に組み合わせることができます。
- 弱いLLMは、強いLLMによって言い換えられた質問からより多くの利益を得ることができます。
- すべてのモデルは質問を言い換えることから利益を得ることができ、より進んだモデルほど大きな改善が期待されます。
- GPT-4は、初回の試みでうまくいかなくても、複数回の言い換えによって概念を明確にする可能性があります。

## Prompt
### one step RaR
質問を言い換えて、それに回答するように指示します。

```
{question}

Rephrase and expand the question, and respond
```

### two step RaR


```
{original question}

Given the above question, rephrase and expand it to help
you do better answering. Maintain all information in the
original question.
```

上記の質問結果から`reshaped question`を取得します。
`original question`と`reshaped question`から新しいプロンプトを作成します。

```
(original) {original question}
(rephrased) {reshaped question}
Use your answer for the rephrased question to answer the
original question.
```
