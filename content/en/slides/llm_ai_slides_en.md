---
title: Large Language Models and Artificial Intelligence
author: Binjian Xin
date: 2023-03-13T00:00:00+08:00
draft: false
slides:
  # Choose a theme from https://github.com/hakimel/reveal.js#theming
  theme: black
  # Choose a code highlighting style (if highlighting enabled in `params.toml`)
  #   Light style: github. Dark style: dracula (default).
  highlight_style: dracula
---

# Large Language Models and Artificial Intelligence

Binjian Xin | 2023-03-13

---

Table of Contents

- [Overview](#overview)
- [Engineering Implementation of Large Language Models](#engineering-implementation-of-large-language-models)
- [Prospect and Challenges](#prospect-and-challenges)

---

## Overview {#overview}

---

### Technological Advancement {#technological-advancement}

{{< figure src="/ox-hugo/technology.png" >}}

- The emergence of new technologies leads to social progress.
- Artificial intelligence is hailed as the electricity of the new era.
- [Jordan Tigani Big Data is Dead](https://motherduck.com/blog/big-data-is-dead/)

{{< speaker_note >}}

The emergence of new technologies leads to social progress, and artificial intelligence is hailed as the electricity of the new era.
Electricity has its drawbacks:

- Danger of electric shock
- Expensive infrastructure
- Eliminate old industries, create new industries and occupations

Big data:
[Jordan Tigani (ex Google Enguineering lead of BigQuery) Big data is dead](https://motherduck.com/blog/big-data-is-dead/)
2011, 2017~2019, big data did not become a bottleneck

- Not reaching the big data level GB
- Storage and computing are being separated
- No new business, data is growing linearly
- People only care about recent data
- Companies that really have big data almost never query all the data, 2017
- Single-machine computing power has increased significantly
  {{< /speaker_note >}}

---

### Updating Scientific Concepts {#updating-scientific-concepts}

{{< figure src="/ox-hugo/science.png" width="40%" >}}

- Three areas have undergone huge, lasting, and profound changes.
- The deeper the understanding of principles, the greater the impact of applications.

{{< speaker_note >}}

Three areas have undergone huge, lasting, and profound changes

- The deeper the understanding of principles, the greater the impact of applications, -> revolutionary applications
  - Physics case: Nuclear fusion, the origin of the universe, the formation of stars, \\(E=MC^2\\), inexhaustible and safe energy source, 50 years later -> 5 years later
  - Biology case: Biochemical origin of eukaryotic cell organisms: Photosynthesis, cellular respiration, mitochondria, research on extraterrestrial life
- Discovering problems is the research direction for progress.
- Deep understanding will change your mind!

[Bill Gates AI Age Has Begun](https://www.gatesnotes.com/The-Age-of-AI-Has-Begun)

- The second revolutionary technological demonstration after GUI, mid-2022 -> September
  {{< /speaker_note >}}

---

#### What is ChatGPT? {#what-is-chatgpt}

<b><u>Chat</u></b> <b><u>G</u></b>enerative <b><u>P</u></b>retrained <b><u>T</u></b>ransformer

- Essence: Intelligence transformed into computation
  - Basic object of calculation: embedded space(**embedding**)
  - Machine learning methods
- Characteristics
  - Large scale
  - Single method (deep learning Transformer architecture)
  - Multilingual mode
  - Strong artificial intelligence (AGI?)
- Open source and open
  - Transferable: image, control
  - Serendipity

{{< speaker_note >}}

- Corpus, training samples
  - until 2003 5 EB ExaByte, 2013 5EB/2 days (1EB: \\(10^9\\) GB, 1 Zettabye: \\(10^{12}\\) GB, billions and billions Carl Sagan)
  - Model, computational power
  - Insufficient training
  - The scale is necessary, but it is likely not sufficient
- Single method (artificial intelligence, machine learning, deep learning, large neural network model, computational model): existed in the 1990s, computational power, rise of the Internet
  - The engineering implementation principle is completely clear, the results need to be interpreted and analyzed, there are disputes
  - Bet, stake, confidence, courage, faith
- Serendipity
  - Hardware lottery GPU
    - 1990 64-node computer network, Jeff Dean, Yoshua Bengio
  - Experts: Li Feifei, Hinton, Bengio, LeCunn
  - The inevitable in the accidental: The biochemical origin of life, the origin of eukaryotes, the origin of language (200,000 years ago); evolution drives exponential growth
- Engineering implementation understanding
  - Visualization, animation (Jay Alammar, Lilian Weng, Christopher Potts)
  - Peeling an onion, layer by layer
    {{< /speaker_note >}}

---

#### Ilya Sutskever NIPS 2015 {#ilya-sutskever-nips-2015}

{{< figure src="/ox-hugo/sutskever_nips2015.png" title="Sutskever 2015" width="30%" >}}

> - If the dataset is large enough
> - And train a large neural network
> - You will definitely succeed!

{{< speaker_note >}}
RNN model, Google Brain
<https://www.youtube.com/watch?v=-uyXE7dY5H0>

{{< /speaker_note >}}

---

#### Large Language Models {#large-language-models}

<!--list-separator-->

- GPT Series
   <!--list-separator-->
  - GPT2 (1.5B), GPT3 (175B), InstructGPT(Alignment, RLHF)， ChatGPT(Data collection differences), GPT4(?)
    👉 NanoGPT (Andrej Karpathy)
    - [ChatGPT for Slack](https://www.salesforce.com/news/wp-content/uploads/sites/3/2023/03/Slack_ChatGPT_Blue.gif)
      {{< figure src="/ox-hugo/Slack_ChatGPT_Blue.gif" title="Neural Network as a Large Language Model" width="40%" >}}

---

#### Large Language Models and Training Computational Power {#large-language-models-and-training-computational-power}

{{< figure src="/ox-hugo/Ai-training-computation.png" width="60%" >}}

{{< speaker_note >}}

- Google: LaMDA(137B),PaLM(540B, Minerva,PaLM-E),BERT(0.34B)
- Meta: Galactica,OPT(175B),LLaMA（65B）
- MS&amp;NV: Megatron(530B)
- DM: **Chinchilla** (70B)
- HF🤗:Bloom(175B)
- EleutherAI: GPT-NEO(2.7B),-J(6B),-NeoX(20B)
- DALL-E, Imagen, Flamingo, Parti, SD
  Model size: Number of neural network parameters (inference), computational power consumed during training

Computational problem!

kiloFlops 10^3, metaFlops 10^6, giga- 10^9 (billion), tera- 10^12 (trillion), peta- 10^15 (quadrillion), exa- 10^18 (quintillion, hundreds of billions of billions, zetta- 10^21 (sextillion), yotta- 10^24, ronna- 10^27, quetta-10^30

Palm Pathway Languane model, -e embodied, open API (3.14)
Chinchilla model and significance: All models: insufficient training, model too large, undertrained
Amazon: AlexaTM(20B)

{{< /speaker_note >}}

---

#### Energy Density Improvement of Lithium Batteries {#energy-density-improvement-of-lithium-batteries}

{{< figure src="/ox-hugo/FOTW_1234.png" width="80%" >}}

---

#### Improvement in Large Language Model Capabilities {#improvement-in-large-language-model-capabilities}

{{< figure src="/ox-hugo/llm-progress.jpg" width="500px" >}}

{{< speaker_note >}}

2012 AlexNet(PC)
2017 Transformer(Attention)
Explosive development

{{< /speaker_note >}}

---

#### Social Impact {#social-impact}

{{< figure src="/ox-hugo/ai_investment.png" alt="AI investment" title="AI investment" width="60%" >}}

- Microsoft invests in OpenAI
- Competition: Microsoft(Sydney), Google(LLaMDA,Bard)，Meta(Galactica,LlaMa),GPT4
- Intelligence, Agency, Sentience, Conciousness, Will

{{< speaker_note >}}

- [Washington Post LaMDA Report](https://www.washingtonpost.com/technology/2022/06/11/google-ai-lamda-blake-lemoine/)
- Fudan Qiu Xipeng MOSS
- The material basis of intelligence?
- Is intelligence an essential part of human nature? (Separating from human nature?)
- Yishan Wong, former reddit CEO (2012-2014) predicted that a certain singularity event would occur by the end of 2023!
  {{< /speaker_note >}}

---

#### [ChatGPT's False Promises](https://www.nytimes.com/2023/03/08/opinion/noam-chomsky-chatgpt-ai.html) {#chatgpts-false-promises}

{{< figure src="/ox-hugo/Noam_Chomsky_portrait_2017_retouched.png" title="Noam Chomsky" width="30%" >}}

> It can be used to solve problems,
> but its concept of language and knowledge is fundamentally flawed.

{{< speaker_note >}}

> The so-called revolutionary advances in artificial intelligence are both worrying and optimistic.
> Optimistic because intelligence can be used to solve problems, worrying because its concept of language and knowledge is fundamentally flawed.

This machine learning method integrates these flawed concepts into our technology and products, thereby devaluing our science and ethics.
The human mind is not, like ChatGPT and its ilk, a lumbering statistical engine for pattern matching, gorging on hundreds of terabytes of data and extrapolating the most likely conversational response or most probable answer to a scientific question. On the contrary, the human mind is a surprisingly efficient and even elegant system that operates with small amounts of information; it seeks not to infer brute correlations among data points but to create explanations.

Criticism: Oxford Summerfield Lab:"Like others, Chomsky pits “pattern matching” vs. “understanding”. this is a sort of neo-dualism: it diminishes computation by asserting that it lacks some intangible quality (as we might diminish other minds by assuming they lacks some intangible quality (as we might diminish other minds by assuming they lack subjectivity)

From a Buddhist perspective, dualism exaggerates "self-nature" and gets obsessed

{{< /speaker_note >}}

---

#### [Yoshua Bengio](https://venturebeat.com/ai/as-gpt-4-chatter-resumes-yoshua-bengio-says-chatgpt-is-a-wake-up-call/) {#yoshua-bengio}

{{< figure src="/ox-hugo/Yoshua_Bengio_2019_cropped.jpg" width="30%" >}}

> ChatGPT is impressive, but scientifically just a small step,
> at best it is an engineering advance.

{{< speaker_note >}}
ChatGPT is impressive, but scientifically just a small step, at best it is an engineering advance. Its main significance is to awaken the public's awareness of the meaning of artificial intelligence.

- 1990s: 1991 "ANN and their application to sequence recognition"
- 2000s: 2003 "A Neural Probabilistic Language Model" Understanding the foundation of large language models!
- 2010s: 2014 "Neural Machine Translation by Jointly Learning to Align and translate"
- 2018 Turing Award
- Before 2010, few believed this method could succeed!

2000s: embedding replaces n-gram n-gram, Markov chain

1.  Mathematical model
2.  Optimization method (expression and implementation method)

{{< /speaker_note >}}

---

## Engineering Implementation of Large Language Models {#engineering-implementation-of-large-language-models}

---

### Use Cases {#use-cases}

{{< figure src="/ox-hugo/nn.png" title="Neural Network as a Large Language Model" width="60%" >}}

{{< speaker_note >}}

- Familiar solutions: image, speech, control, chess, natural language
- Regardless of whether the input source is continuous or discrete, it is a processing method: natural language is essentially discrete, image, speech and control strategies are essentially continuous. (?)
- Multilayer perceptron is the most generalized neural network, containing all other network types. Disconnect some connections, such as convolutional network
- Signal mathematical model + signal processing model (network)

{{< /speaker_note >}}

---

### Language Encoding Models: Morphemes and n-grams (n-gram) {#language-encoding-models-morphemes-and-n-grams--n-gram}

{{< figure src="/ox-hugo/ngram-example.png" title="n-gram (n-gram)" width="500px" >}}

{{< speaker_note >}}

- Morpheme design parameter selection: letters, phonemes, syllables, words,
- Statistical method optimization selection (unsupervised learning, Byte-Pair-Encoding): google sentencepiece; openai tiktoken
- Markov chain: Complexity follows the curse of dimensionality
  {{< /speaker_note >}}

---

### Computational Objects in GPT: Embedding (embedding) {#computational-objects-in-gpt-embedding--embedding}

{{< figure src="/ox-hugo/word2vec.png" width="50%" >}}

1.  Embedding (encoding of words/morphemes)
    - Independent semantics, repeated in different positions in sentences/texts, reusable variables
    - Corresponds to qualia (Quolia): The clustering of concepts (colors) in consciousness, language is just an interface
2.  Mutual relationships are confirmed by calculation.
3.  Learn through training samples, collect semantics determined by syntax

{{< speaker_note >}}

- [Pretrained Embedding Space (tensorflow)](https://projector.tensorflow.org/)
- Embedded space (embedding): conceptual space, (statistically determined)
- Embedding is not a morpheme, it is obtained by encoding morphemes, and needs end-to-end training, token token, approximately equal to a word, 100 tokens approximately equal to 75 words
- Embedding corresponds to concepts in human language (quolia): discrete, absorbed. (Yoshua Bengio: quolia, discrete, the center of gravity of the conceptual space)
- Linear combination, simple matrix operations
- The weight coefficients of the network: the coefficients of matrix operations, corresponding to the connection between these concepts
- Neural network: Distributed expression model

{{< /speaker_note >}}

---

### Operations of Embedding (embedding) {#operations-of-embedding-embedding}

{{< figure src="/ox-hugo/king-colored-embedding.png" alt="King, Man, Woman" title="Embedding vector" width="80%" >}}

{{< figure src="/ox-hugo/king-man-woman-embedding.png" title="Latent space clustering distribution" width="80%" >}}

{{< speaker_note >}}

Data (words) themselves are structured, mutual relationships, frequency of occurrence, similarity, commutativity, position (grammar, syntax) meaning.
Expressed distributively by neural networks: relationships between concepts, operations (neural impulse conduction)

There is a pattern in all things, and it's part of our universe. It has symmetry, elegance, and grace — those qualities you find always in that which the true artist captures. You can find it in the turning of the seasons, in the way sand trails along a ridge, in the branch clusters of the creosote bush or the pattern of its leaves.
We try to copy these patterns in our lives and our society, seeking the rhythms, the dances, the forms that comfort. Yet, it is possible to see peril in the finding of ultimate perfection. It is clear that the ultimate pattern contains it own fixity. In such perfection, all things move toward death.
“There is in all things a pattern that is part of our universe. It has symmetry, elegance, and grace - those qualities you find always in that which the true artist captures. You can find it in the turning of the seasons, in the way sand trails along a ridge, in the branch clusters of the creosote bush or the pattern of its leaves.
We try to copy these patterns in our lives and our society, seeking the rhythms, the dances, the forms that comfort. Yet, it is possible to see peril in the finding of ultimate perfection. It is clear that the ultimate pattern contains it own fixity. In such perfection, all things move toward death.” ~ Dune (1965)

{{< /speaker_note >}}

---

### Clustering of Embedding (embedding) {#clustering-of-embedding-embedding}

{{< figure src="/ox-hugo/queen-woman-girl-embeddings.png" title="Latent space clustering distribution" width="40%" >}}

{{< figure src="/ox-hugo/king-analogy-viz.png" title="Latent space clustering distribution" width="40%" >}}

{{< speaker_note >}}

Data (words) themselves are structured, mutual relationships, frequency of occurrence, similarity, commutativity, position (grammar, syntax) meaning.
Expressed distributively by neural networks: relationships between concepts, operations (neural impulse conduction)

There is a pattern in all things, and it's part of our universe. It has symmetry, elegance, and grace — those qualities you find always in that which the true artist captures. You can find it in the turning of the seasons, in the way sand trails along a ridge, in the branch clusters of the creosote bush or the pattern of its leaves.
We try to copy these patterns in our lives and our society, seeking the rhythms, the dances, the forms that comfort. Yet, it is possible to see peril in the finding of ultimate perfection. It is clear that the ultimate pattern contains it own fixity. In such perfection, all things move toward death.
“There is in all things a pattern that is part of our universe. It has symmetry, elegance, and grace - those qualities you find always in that which the true artist captures. You can find it in the turning of the seasons, in the way sand trails along a ridge, in the branch clusters of the creosote bush or the pattern of its leaves.
We try to copy these patterns in our lives and our society, seeking the rhythms, the dances, the forms that comfort. Yet, it is possible to see peril in the finding of ultimate perfection. It is clear that the ultimate pattern contains it own fixity. In such perfection, all things move toward death.” ~ Dune (1965)

{{< /speaker_note >}}

---

### Embedding in Images {#embedding-in-images}

{{< figure src="/ox-hugo/image_embedding.png" title="Image embedding" width="80%" >}}

1.  Image embedding encoding and decoding, obtained through DCGAN training
2.  Interpolation of embedding parameters: continuous change of images (male -> female)
3.  Vector operation of embedding: modification of images

{{< speaker_note >}}

- Alec Radford now at OpenAI, credit for OpenAI LLM

{{< /speaker_note >}}

---

### [GPT3 Training](https://jalammar.github.io/how-gpt3-works-visualizations-animations/) {#gpt3-training}

{{< figure src="/ox-hugo/01-gpt3-language-model-overview.gif" alt="Overview" title="overview" width="30%" >}}

{{< figure src="/ox-hugo/02-gpt3-training-language-model.gif" alt="training" title="Training" width="30%" >}}

{{< speaker_note >}}

1.  Pretrained model generates text
2.  Single large model training: 355GPU years $4.6M, 300 B (token, word, stem/root)
3.  Training sample generation
4.  Training: Predict the next word, adjust parameters based on the target (175 B)
5.  Data
    - Network text
    - Code
    - English
6.  Training based on context understanding

{{< /speaker_note >}}

---

### [GPT3 Sample Input](https://jalammar.github.io/how-gpt3-works-visualizations-animations/) {#gpt3-sample-input}

{{< figure src="/ox-hugo/gpt3-training-examples-sliding-window.png" alt="training samples" title="training samples" width="30%" >}}

{{< figure src="/ox-hugo/03-gpt3-training-step-back-prop.gif" title="Latent space clustering distribution" width="30%" >}}

{{< speaker_note >}}

1.  Pretrained model generates text
2.  Single large model training: 355GPU years $4.6M, 300 B (token, word, stem/root)
3.  Training sample generation
4.  Training: Predict the next word, adjust parameters based on the target (175 B)
5.  Data
    - Network text
    - Code
    - English
6.  Training based on context understanding

{{< /speaker_note >}}

---

### [GPT3 Inference](https://jalammar.github.io/how-gpt3-works-visualizations-animations/) {#gpt3-inference}

{{< figure src="/ox-hugo/04-gpt3-generate-tokens-output.gif" alt="output" title="output" width="30%" >}}

{{< figure src="/ox-hugo/gpt3-parameters-weights.png" alt="weights" title="weights" width="30%" >}}

{{< speaker_note >}}

1.  Generative model: Inference generates one word at a time; sequence, autoregressive model; sampling from a probability distribution, it is random. The root cause of multi-modality.
2.  Unsupervised learning pretraining generates useful parameters
3.  Maximum context length: 2048 (2k);GPT-4 0.03+0.06/1k@8k, 0.06+0.12/1k@32k; ColT5 64K, autoregressive model
4.  Basic steps: 1. Convert words to embedding (encoding), 2. Predict, 3. Restore embedding to words (decoding): Embedding encoding is obtained through end-to-end training.

{{< /speaker_note >}}

---

### [GPT3 Context and Embedding](https://jalammar.github.io/how-gpt3-works-visualizations-animations/) {#gpt3-context-and-embedding}

{{< figure src="/ox-hugo/05-gpt3-generate-output-context-window.gif" alt="context window" title="context window" width="30%" >}}

{{< figure src="/ox-hugo/06-gpt3-embedding.gif" title="Embedding space" width="30%" >}}

{{< speaker_note >}}

1.  Generative model: Inference generates one word at a time; sequence, autoregressive model; sampling from a probability distribution, it is random. The root cause of multi-modality.
2.  Unsupervised learning pretraining generates useful parameters
3.  Maximum context length: 2048 (2k);GPT-4 0.03+0.06/1k@8k, 0.06+0.12/1k@32k; ColT5 64K, autoregressive model
4.  Basic steps: 1. Convert words to embedding (encoding), 2. Predict, 3. Restore embedding to words (decoding): Embedding encoding is obtained through end-to-end training.

{{< /speaker_note >}}

---

### [GPT3 and Transformer](https://jalammar.github.io/how-gpt3-works-visualizations-animations/) {#gpt3-and-transformer}

{{< figure src="/ox-hugo/07-gpt3-processing-transformer-blocks.gif" alt="Overview" title="overview" width="30%" >}}

{{< figure src="/ox-hugo/08-gpt3-tokens-transformer-blocks.gif" alt="training" title="Training" width="30%" >}}
{{< speaker_note >}}

1.  96 transformer decoding layers, each decoding layer parameters ~1.8B
2.  Decoding process
3.  App React code generation
4.  Transfer learning (fine-tuning for specific tasks): InstructGPT, ChatGPT

<https://twitter.com/i/status/1284421499915403264>

{{< /speaker_note >}}

---

### [GPT3 Applications](https://jalammar.github.io/how-gpt3-works-visualizations-animations/) {#gpt3-applications}

{{< figure src="/ox-hugo/09-gpt3-generating-react-code-example.gif" alt="training samples" title="Code generation" width="30%" >}}

{{< figure src="/ox-hugo/10-gpt3-fine-tuning.gif" title="Fine-tuning" width="30%" >}}

{{< speaker_note >}}

1.  96 transformer decoding layers, each decoding layer parameters ~1.8B
2.  Decoding process
3.  App React code generation
4.  Transfer learning (fine-tuning for specific tasks): InstructGPT, ChatGPT

<https://twitter.com/i/status/1284421499915403264>

{{< /speaker_note >}}

---

### ChatGPT {#chatgpt-overview}

{{< figure src="/ox-hugo/ChatGPT_Diagram.svg" title="Two-stage training" width="50%" >}}

- GPT3.5: codex
- Supervised learning, fine-tuning
- Reinforcement learning (PPO) constructs a reward function
- Train improved models using reinforcement learning

{{< speaker_note >}}

- Code is a high-quality language
- English is a strictly formalized language (Montayou)
- Chinese: graphic characters, insufficient diversity in pronunciation, polyphonic characters, homophones, heavily rely on context. The advantages of images, the disadvantages of pronunciation, certain ambiguity in semantic expression, seemingly true but not. Homophones.
- Chinese sample training (as a supplement)
- Chomsky: Universal grammar theory, being able to learn foreign languages, the fundamental of translation.
- Meta, translation aligns the mapping relationship between two embedding spaces.

- Why reinforcement learning?: Solve the problem of long-term rewards.

{{< /speaker_note >}}

---

#### Emergent Behavior ([[Emergence Behavior](https://www.jasonwei.net/blog/emergence)) {#emergent-behavior-emergence-behavior}

{{< figure src="/ox-hugo/emergence.gif" title="Emergence Ablities on Benchmarks" width="30%" >}}

{{< figure src="/ox-hugo/emergence_behavior.jpeg" title="Emergence Behavior" width="30%" >}}

{{< speaker_note >}}

Temperature as a physical phenomenon: Liquid water, steam, water molecules reach a certain level before they appear

{{< /speaker_note >}}

---

### Application and Deployment {#application-and-deployment}

- Prompt Engineering
- LLaMA Remakes GPT (Stanford [Alpaca](https://crfm.stanford.edu/2023/03/13/alpaca.html) 7B, $100)
  - Train by API comparison ➡ Business model?
- LLaMA (7B) Raspberry Pi port (4GB, 10sec/token)

{{< speaker_note >}}

Prompt engineering:
Humans supplement long logical dependency problems to compensate for the neural network's long sequence understanding problem (2k sequence length),
Dialogue with artificial intelligence:

- Accurately describe input requirements
- Match model multi-modality

{{< /speaker_note >}}

---

### Transformer {#transformer}

{{< figure src="/ox-hugo/transformer.png" alt="Transformer and attention" width="40%" >}}

- Structure: Less inductive bias, better generalization
  - Attention: Self-attention, cross-attention, multi-head self-attention
  - MLP, multilayer perceptron
  - Residual structure
- Requires a large number of training samples
- Network scale and dataset

{{< speaker_note >}}

Positional encoding
Layer normalization
GPT3
Soft attention, hard attention
Convolutional network weight coefficients generated by another network: Second-order network

{{< /speaker_note >}}

---

### Disputes {#disputes}

#### [ChatGPT is a Blurry JPEG of Reality](https://www.newyorker.com/tech/annals-of-technology/chatgpt-is-a-blurry-jpeg-of-the-web) {#chatgpt-is-a-blurry-jpeg-of-reality}

{{< figure src="/ox-hugo/Chiang.gif" width="50%" >}}

- Similar to lossy compression of original images with jpeg images
- Inaccurate description of reality leads to distortion and misinformation
- Model hallucination problem contaminates corpus and information

{{< speaker_note >}}

- Similar to lossy compression of original images with jpeg images
- Inaccurate description of reality leads to distortion and misinformation
- Model hallucination problem (hallucination), contaminates corpus and information
- Lossy compression appears more intelligent

Efficient and rapid amplification of contamination problems by generative models
Markus Hutter Prize 2006 Intelligence is a compression, lossless compression: 1GB wiki -> 115MB

{{< /speaker_note >}}

---

#### [GPT4 and the Uncharted Territories of Language](https://www.fast.ai/posts/2023-03-20-wittgenstein.html) {#gpt4-and-the-uncharted-territories-of-language}

“They (LLM) could also create new ethical, social, and cultural challenges that require careful reflection and regulation. How we use this technology will depend on how we recognize its implications for ourselves and others.

But when we let GPT4 do this for us, are we not abdicating our intelligence? Are we not letting go of our ability to choose, to pick out, to read? Are we not becoming passive consumers of language instead of active producers?”

GPT4 Response
prompted by Jeremy Howard
on 2023.02.23

{{< speaker_note >}}

“They (LLM) could also create new ethical, social, and cultural challenges that require careful reflection and regulation. How we use this technology will depend on how we recognize its implications for ourselves and others.

This technology is a form of “Artificial Intelligence”. “Intelligence” derives from inter- (“between”) and legere (“to choose, pick out, read”). To be intelligent, then, is to be able to choose between things, to pick out what matters, to read what is written. Intelligence is not just a quantity or a quality; it is an activity, a process, a practice. It is something that we do with our minds and our words.

But when we let GPT 4 do this for us, are we not abdicating our intelligence? Are we not letting go of our ability to choose, to pick out, to read? Are we not becoming passive consumers of language instead of active producers?”

Jeremy Howard 2023.02.23
[GPT 4 and the Uncharted Territories of Language](https://www.fast.ai/posts/2023-03-20-wittgenstein.html)

“The limits of my language mean the limits of my world.” — Ludwig Wittgenstein

They could also create new ethical, social, and cultural challenges that require careful reflection and regulation. How we use this technology will depend on how we recognize its implications for ourselves and others.

This technology is a form of “Artificial Intelligence”. “Intelligence” derives from inter- (“between”) and legere (“to choose, pick out, read”). To be intelligent, then, is to be able to choose between things, to pick out what matters, to read what is written. Intelligence is not just a quantity or a quality; it is an activity, a process, a practice. It is something that we do with our minds and our words.

But when we let GPT 4 do this for us, are we not abdicating our intelligence? Are we not letting go of our ability to choose, to pick out, to read? Are we not becoming passive consumers of language instead of active producers?

{{< /speaker_note >}}

---

#### [Intelligence and Coherence Issues](https://sohl-dickstein.github.io/2023/03/09/coherence.html) {#intelligence-and-coherence-issues}

{{< figure src="/ox-hugo/int_coh_cartoon_1.png" title="Intelligence and Coherence" width="80%">}}

---

#### The Higher the Intelligence, the More Chaotic {#the-higher-the-intelligence-the-more-chaotic}

{{< figure src="/ox-hugo/int_coh_life.png" title="Biological Intelligence Coherence" width="30%" >}}

{{< figure src="/ox-hugo/int_coh_organization.png" title="Coherence of Social Organization" width="30%" >}}

---

#### Coherence of Neural Networks {#coherence-of-neural-networks}

{{< figure src="/ox-hugo/int_coh_machines.png" title="Coherence of Neural Networks" width="800pix" >}}

---

## Prospect and Challenges {#prospect-and-challenges}

- Efficiency, openness, origin, effectiveness, synthesis
  - Retrieval-based (search-based) natural language processing
- "Last Mile" of Large Language Models
- Network structure understanding
  - Maintenance, efficient updates
- Disadvantages
  - Long paragraphs
  - Long logical reasoning (chain-of-thought reasoning)
    👉 Reinforcement learning?
  - Contamination of natural language corpus space

Please translate the above markdown file in English to Chinese.

