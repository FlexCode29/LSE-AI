# LSE-AI
LSE AI lab focused on LLM interpretability

Proposal by [Marco Molinari](https://www.linkedin.com/in/marco-molinari-quant/), m.molinari1@lse.ac.uk

## Context

LLM technology is set to significantly impact Data Science, Finance, Education, and many other fields. Tools such as ChatGPT, Bard, and Grammarly have already seen mass adoption, but we remain oblivious to how they work. Further research in how to interpret LLMs would not only yield a greater understanding LLM themselves, but also of how they learn and interpret ideas that we may wish to know more about ourselves. For example: how did LLMs code a state of the art sorting algorithm (FunSearch paper)? How would LLMs decide wether to buy or sell a stock? how would LLMs decide who to vote for?. Moreover, given the plurality of models available (Bard, GPT, Gemini, Claude) we would be able to experimentally check wether our findings generalise, which would further strengthen hypothesis about any circuit we may find.

Findings are to be published in NeurIPS (May) or ICLR (Sep)

## Objectives

Understand exactly what circuits LLMs use for a given task and how do they work, some natural language examples:

- Identifying a Preliminary Circuit for Predicting Gendered Pronouns in GPT-2 Small ([already being done](https://cmathw.itch.io/identifying-a-preliminary-circuit-for-predicting-gendered-pronouns-in-gpt-2-smal))
- Interpreting memorisation. Sometimes [GPT knows phone numbers](https://bair.berkeley.edu/blog/2020/12/20/lmmem/). How?
- how are 3 letter acronyms interpreted, like "The Acrobatic Circus Group (ACG) and the Ringmaster Friendship Union -> RFU

Some alghorithmic tasks:

- Train a model on multiple algorithmic tasks we understand (like modular addition and subtraction). Compare to a model trained on each task. Does it learn the same circuits? Is there superposition?
- 5 digit multiplication
- how does a model find permutations of a list? how does it sort a list?

One great paper doing this in the past on indirect object identification: **[Interpretability in the Wild: a Circuit for Indirect Object Identification in GPT-2 small](https://arxiv.org/abs/2211.00593)** (ICLR)

We aim at establishing synergies with other labs/research lines within LSE that make use of LLMs.

## Methodologies:

1. Identify a behaviour (like Indirect Object Identification) in a model to investigate
2. Try to **understand the behaviour as a black box. Feed in a lot of inputs with many variations and see how the model’s behaviour changes. What does it take to break the model’s performance? Can we confuse it or trip it up? Form hypotheses about what the model is doing - how *could* a transformer implement an algorithm for this?
3. Run experiments to support/falsify these hypotheses using [transformer lens](https://github.com/neelnanda-io/TransformerLens/). Perform Layer Attribution, Head Attribution,  Decomposing Heads, Attention Analysis. Iterating fast
4. Regularly red-team and look for if there’s a boring explanation for what’s going on, or a flaw in the techniques, what could it be? How could we falsify?
5. Once we have some handle on what’s going on, try to scale up and be more rigorous - look at many more prompts, use more refined techniques like path patching on bigger state-of-the-art models and causal scrubbing, try to actually reverse engineer the weights, etc.

The authors of the IOI paper have recently published **[Towards Automated Circuit Discovery for Mechanistic Interpretability](https://arxiv.org/abs/2304.14997)** (NeurIPS) further improving the techniques listed above

## Timeline

January weeks 2-4: recruit and train, look in courses such as, MA333 (Optimisation for Machine Learning), DS105 (data for data science), ST310 (Machine Learning), ST311 (Artificial Intelligence), ST456 (Deep Learning), ST449 (Artificial Intelligence and Deep Learning). Train following: [Concrete Steps to Get Started in Transformer Mechanistic Interpretability](https://www.neelnanda.io/mechanistic-interpretability/getting-started) by Neel Nanda (de facto inventor of the field)

February: narrow the problem statement via exploratory ideation/experimentation/red-team falsification. Decide which specific circuit to investigate (either one of the above or a better one)

March-April: rigorously dive into mechanics of the problem

May: redact paper and submit to NeurIPS

## Support

We aim to make LSE a significant player in the interpretability field within this academic year, and in order to achieve that we are so far expect the following support:

- Stanford partnership: [Federico Bianchi](https://scholar.google.com/citations?user=1okGjb8AAAAJ) (postdoc featured in [ACL](https://www.aclweb.org/anthology/2020.acl-main.154.pdf), [ICLR](https://openreview.net/forum?id=KRLUvxh8uaX), [Nature Medicine](https://www.nature.com/articles/s41591-023-02504-3)) for a weekly call, and core team researcher [Davide Ghilardi](https://www.linkedin.com/in/davide-ghilardi-9407191a0/)
- Harvard correspondant: [Valerio Pepe](https://www.linkedin.com/in/valerio-pepe/), Harvard CS, possible core team researcher and link with [Neel Nanda](https://www.linkedin.com/in/neel-nanda-993580151/) (Interpretability team Lead @Deepmind, inventor of the field)
- Qi4M industry partner: AI fintech company where I authored my [first ML paper](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4246289), possibly  investing GPU time and partnering for a financial AI research line (possibly interpretability)
- New OpenAI research grant: $10.000.000 in [Superalignment Fast Grants](https://openai.com/blog/superalignment-fast-grants) have been launched by OpenAI for research in: AI interpretability/weak to strong generalisation/scalable oversight. These are specifically for new academic labs entering the field like ours, will apply by Feb 14th with narrower problem.

### We ask the LSE DSI for the following:

- space: desks/a room
- GPUs: access to the T4s on Fabian, and to new clusters when available
- recognition: hosting our repo on the DSI GitHub
