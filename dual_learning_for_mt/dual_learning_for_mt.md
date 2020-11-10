## [Dual Learning For Machine Translation](https://papers.nips.cc/paper/2016/hash/5b69b9cb83065d403869739ae7f0995e-Abstract.html)

**TLDR;** The authors cast machine translation as a game of a primal task and a dual task, which allows two agents to teach each other in a reinforcement learning fashion (i.e., policy gradient method). With this implementation, the agent only requires monolingual English <-> French text data (with 10% bilingual warmup) to achieve a comparable performance to NMT trained with pure bilingual data.

### Key Points

- The motivation is that parallel data are scarce and costly to collect.
- The translation models are trained from unlabeled data through RL.
- For the policy gradient method, it used REINFORCE since no advantage function appears.
- The system reduces the requirement on aligned bilingual data.
- The two-agent game:
    - *A* sends a message in language *A* to a noisy channel, which converts that message to language *B* and further transmits to *B*.
    - *B* tells if the received message is **natural** and inform *A*, and then sends it back to *A* using the other noisy channel.
    - *A* tells if the received message is **correct** (consistent with the original message). This allows both *A* and *B* to know that whether the two channels perform well.
    - The game can start from either side, but it is a symmetric process in either one of the two cases. The two channels are improved using the feedback signal.
- The LM reward is the naturalness of the output sentence, whereas the communication reward is the log probability of the sentence recovered from the middle translation output. The total reward is the sum of both.
- It maximizes towards the expected sum of the two rewards over the middle translation outputs.
- It uses beam search to obtain more meaningful results?

### Notes and Questions

- Cna we implement advantage function here? If so, does lower variance help?
- What are sampling technique can be used?
- Why can beam search obtain more meaningful results?