## [Experience Grounds Language](https://arxiv.org/abs/2004.10151v2)

**TLDR;** Current models trained only from text corpora might hinder the language understanding research because the supervision from text alone can be limited, so we need to embed social context. The authors proposed the notion of World Scopes (WS), which considers not only the text corpus but also grounding, embodiment, and social interaction.

### Key Ideas

- WS1: Corpus
    - Finding formal linguistic structure
    - Unstructured representations
- WS2: Internet
    - Large web-crawls: unstructured, unlabeled, multi-domain, and multilingual data
    - Assumption: everything that needs knowing can be learned from the written world
    - Truth: models are only blindly searching for symbolic co-occurrences void of meaning
    - Adding more parameters helps, but the slope of the increase is decreasing quickly
    - Models do not necessarily capture the contextual meaning
- WS3: Perception
    - Auditory, tactile, and visual input
    - Richer signal for supervision that text cannot provide
    - More like how humans learn
    - Help long-tail generalization (e.g., zero-shot test cases)
- WS4: Embodiment
    - Situated action taking
    - Planning through trial-and-error
    - Humans have unlimited supervision from the environment
    - Allows the agent to construct rich pre-linguistic representations (e.g., transfer from 2d world to 3D world)
    - Some knowledge is incommunicable by language, but still require to understand the language
- WS5: Social
    - Generate language that does something to the world
    - Theory of mind: the ability to consider the feelings and knowledge of others
    - Static datasets are problematic because of the risk of learning spurious patterns and bias
    - Cross entropy loss discourage learning the tail of the distribution
    - Needs learning by participation/interaction

### Notes and Questions