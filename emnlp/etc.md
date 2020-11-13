## [ETC: Encoding Long and Structured Inputs in Transformers](https://arxiv.org/abs/2004.08483v5)

**TLDR;** ETC encodes long inputs using global-local attention and represents structures by combining relative position representations and flexible masking. It also employs CPC pre-training for hierarchical global tokens (structures).

### Key Points

- Global-local attention: input tokens divided into two sets
    - Global: can attend to all input tokens
    - Long: can only locally attend to nearby tokens
    - Related to [Longformer](https://arxiv.org/abs/2004.05150v1).
- [Relative position representations](https://arxiv.org/abs/1803.02155v2): allow encoding arbitrary structure relations between input tokens.
- [Contrastive predictive coding (CPC)](https://arxiv.org/abs/1807.03748v2): pre-training objective that helps the model learn how to use global summary tokens.
- The experiments use benchmarks with long/structured data
    - Question answering: Natural Questions (NQ), HotpotQA, WikiHop
    - Keyphrase extraction: OpenKP
- It was pre-trained using BERT original datasets but filtering out documents with fewer than 7 sentences.
    - MLM
    - CPC
    - Lifting weights directly from RoBERTa (with RoBERTa's vocabulary)


### Notes and Questions
