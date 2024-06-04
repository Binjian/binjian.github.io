---
title: Fundamental Models and Applications
author: Binjian Xin
date: 2023-06-02T00:00:00+08:00
draft: false
slides:
  # Choose a theme from https://github.com/hakimel/reveal.js#theming
  theme: black
  # Choose a code highlighting style (if highlighting enabled in `params.toml`)
  #   Light style: github. Dark style: dracula (default).
  highlight_style: dracula
---

# Fundamental Models and Applications

Xin Binjian | 2023-06-02

---

Table of Contents

- [Overview](#overview)
- [Engineering Significance](#engineering-significance)
- [Applications](#applications)
- [Moats](#moats)

---

<!--endtoc-->

## Overview {#overview}

---

### ("Fundamental Model", "Human Brain") ∈ "General Intelligence" {#fundamental-model--human-brain--and-isin--general-intelligence}

{{< figure src="/ox-hugo/IntelligenceBigPicture.png" width="80%" >}}

- Neural network models embody intelligence different from humans.
- "You can't cut butter with a knife made of butter."
- "What is intelligence?" --> "What can intelligence do?"

{{< speaker_note >}}

- Neural network-based fundamental models embody intelligence different from humans.
- Greater significance: Fundamental models trigger the evolution of understanding intelligence: "You can't cut butter with a knife made of butter."
- Artificial intelligence as a discipline: "What is intelligence?" --> "What can intelligence do?", a better research method to avoid unnecessary philosophical discussions and irrelevant rhetoric.
- Machine learning is the primary method.
- Fundamental models are tools: more importantly, they reveal the nature of intelligence.

  {{< /speaker_note >}}

---

### Understanding is the Premise of Application {#understanding-is-the-premise-of-application}

- ✅ Intelligence
  - Intelligence itself: The choice of network architecture may be accidental.
  - Neural network models: Structure conforms to physical reality.
- ❎ Safety
  - Regulations, testing, licensing.
- ❎ Alignment
  - General intelligence -> Human-like intelligence.

{{< speaker_note >}}

Two meanings:

- Intelligence itself: The choice of network architecture may be accidental, it may not be a transformer model.
- Neural network models: Inevitability in chance. Structure conforms to physical reality.

Safety and Alignment:

- Laws and regulations restrict the capabilities of applied models.
- Testing.
- Licensing.

  {{< /speaker_note >}}

---

### Invention or Discovery? {#invention-or-discovery}

- ❎ **Constructing** artificial intelligence using neural networks.
- ✅ **Discovering** the phenomena and laws of intelligence through neural networks.

  > With a large and deep model,
  > a large amount of data in a certain field (image recognition, natural language understanding),
  > the correct optimization method and sufficient computing resources, it will definitely succeed.
  >
  > - Ilya Sutskever

{{< speaker_note >}}

- It's not that the methods have improved, but reality has changed. Reality is the strongest driving force!
- Ilya Sutskever's irreducible arguments:

  1.  Premise: Large and deep neural networks can exhibit intelligence (human brain).
  2.  Large and deep models (convolutional networks, LSTM, Transformer).
  3.  A large amount of data describing a certain task (image recognition, natural language understanding) (complete, not necessarily well-organized).
  4.  Training methods (optimization, engineering resources).

  {{< /speaker_note >}}

---

### "Simple" ≠ "Easy"! {#simple--and-ne--easy}

- Seemingly simple, slow to be accepted.
- Simple ideas/methods are not easily accepted.
- Transformer
  - Relatively simple structure.
  - High computational saturation.
  - Dynamic message passing.

{{< speaker_note >}}

- Seemingly simple, slow to be accepted.
- Simple ideas/methods are not easily accepted.
  - The idea of evolution is from biology, simple but not easy, slowly permeating.
  - Simple but profound ideas: wide applications, in different fields! (Mysterious).
- Simple Transformer: attention, mlp, high computational saturation (efficient use of hardware), message passing mechanism, graph neural network, multi-head attention.

  {{< /speaker_note >}}

---

## Engineering Significance {#engineering-significance}

---

### Fundamental Large Models are the Source of High Model Capabilities {#fundamental-large-models-are-the-source-of-high-model-capabilities}

- GPT3, GPT4 costs are "eyewatering"!
- LLaMA
  - 7.4 million A100 machine hours (856 years, $15M).
- Fundamental models are large and efficient.
- Large models are not sufficient, but necessary.
  - Large models have about 1 trillion connections (the brain has 100 trillion connections).

{{< speaker_note >}}

- Sam Altman: to raise $100 billion, 2022 deficits 0.5bio, 700k~1m/daily (inference) for GPT-3.
- <https://www.mosaicml.com/blog/training-stable-diffusion-from-scratch-costs-160k#:~:text=We%20estimated%20an%20upper%2Dbound,model%20card%20from%20Stability%20AI>.
  - Costs include testing, iteration x4.
    - Stability AI 5400x2 months, total cost x4 (testing, expert iteration, $15M x4).
    - Stability AI for Stable Diffusion V2:
      - 79K A100 machine hours, $160K; V1 300~400K.
- LLaMA: Apache 2 License!
- Georf Hinton: 1 trillion connections (the human brain has 100 trillion connections, billions of neurons).

  - Forward-Forward &pr; Back-Propagation (Jeff Hinton).

  {{< /speaker_note >}}

---

### AGI Invention 👉 Electricity/Car/Atomic Bomb Invention {#agi-invention--electricitycaratomic-bomb-invention}

- The emergence of new technologies leads to social progress.
- Not everyone knows:
  - Increasing the size of autoregressive models + expanding training 🔜 Artificial General Intelligence!!!
- The eve of a surging revolution.

{{< speaker_note >}}

- Artificial intelligence is hailed as the electricity of the new era.
  - Electricity has its downsides:
    - Risk of electric shock.
    - Expensive infrastructure.
    - Eliminates old industries and creates new industries and professions.
  - The invention of the car (popularization, if you don't use it, others will, it's a matter of time and experience accumulation).
- No one can predict accurately: even for fundamental model developers, shock!!!

  - Google Brain 2017 Tensor2Tensor, building multimodal large networks (Aidan Gomez) invented the transformer architecture, the idea was already there 10 years ago, inevitable.
    - No mode collapse appeared.
    - Predicting the next word —> similar to AGI, reasoning ability.
  - No one could have predicted 5 years ago: perhaps including OpenAI.
  - Need further understanding and research on LLMs.

  {{< /speaker_note >}}

---

### AGI Cambrian Explosion {#agi-cambrian-explosion}

> Natural selection R&D vs. Human engineering R&D
>
> --- Daniel Dennett

- Infrastructure.
- Search.
- Applications and software/hardware development methods.

{{< speaker_note >}}

- Most evident during the Cambrian period: Natural selection as a designer.
  - Rich and diverse evolution.
    - Disorder.
    - Blindness.
    - Cost, a lot of elimination.
    - The uncompetitive are eliminated.
      - Passive adaptive evolution.
      - Active evolution (understanding, analysis).
  - Eventually, a few dominant species will thrive, and there will be imperfections.
  - Scientific and engineering research is actually reverse engineering of natural selection, and artificial intelligence research is even more so.
- Sam Altman @Y-Combinator: Invest in exponentially growing technologies.
- Infrastructure: toolchains, model structures, cloud facilities (Azure, GCP, AWS, hardware architectures, mobile applications (search, content assistants), intelligent assistants (Siri, Alexa,...), development, programming languages (mojo), deployment.
- Search: perplexity.ai, you.com, Google, Bing.
- Application of information and software technology: changes in technology generations, replacing engineering iterative development methods.
  - Mobileye,... Existing detection technologies are outdated.
- Not just performance, but progress in computational optimization, LLM on Raspberry Pi, 4-bit Quantization).
- Evolution, or natural selection.

  {{< /speaker_note >}}

---

### How to Explain "Emergent Capabilities"? {#how-to-explain--emergent-capabilities}

- Emergent Capabilities
  - Comprehension ability.
  - Common sense.
  - Reflecting on reductionism.
- The physics of artificial intelligence.
  - Experimental discoveries, unpredictable by theory.
  - Quantitative change to qualitative change.

{{< speaker_note >}}

- One understanding: a new perspective on reality, reflecting on reductionism.
  - Regularity at the macro level, iteration from the micro level may have endless complexity (traditional systems theory, not necessarily better).
- Building houses and bridges before Newtonian mechanics, the crystallization (mapping) of all known knowledge/facts/laws.

  {{< /speaker_note >}}

---

### Computer Model of Neural Networks {#computer-model-of-neural-networks}

- Turing machine
  - Software computer.
  - Engineering -> von Neumann machine.
  - Memory bottleneck of the von Neumann architecture.
- Autoregressive neural networks
  - Different memory types, no von Neumann bottleneck.
  - 👉 Different computing chips?

{{< speaker_note >}}

- Turing machine:
  - Computers are fundamentally conceptual creations.
  - Abstract conceptual design, disproving uncomputability.
  - Software computer, the broadest definition -> von Neumann engineering.
- Von Neumann bottleneck.
- Transformer may be a transitional type.
- Nvidia's trillion-dollar market value.

  {{< /speaker_note >}}

---

### The Essence of Fundamental Models {#the-essence-of-fundamental-models}

- Mapping of all knowledge (existing) / reality / laws.
  - Joint probability distribution.
  - Language-constructed world model.
  - Network structure reflects abstract attributes of reality.
- The use of question-answering (reasoning) is a form of information retrieval.
  - Information length, compression ratio -> reasoning, memory.
  - Interface is embedded! Reality mapped to a one-dimensional embedded sequence.
  - Vector database (Pinecone): query, retrieval (prediction).

{{< speaker_note >}}

- Language and Reality
  - Five aggregates (five basic elements of human existence) form (five roots, five senses, eyes, ears, nose, tongue, body) vs. perception (mapping of perception in the mind, clustering), individual understanding, group; concept BoW clustering.
  - Entity/concept: embedded vector.
  - Components and prerequisites of intelligence, a link to the real world.
  - Important abstract attributes of reality: algebra, geometry.
- Abstraction/Classic (Symbolic AI & boolean), Prototype (Vector space), Functional space (manifold), Symmetry-based (Group, transformation invariant).

  - Mathematical mechanism of neural network models:
    - Algebra (symbols, vector space): size, order, causality, combination, association.
    - Geometry (symmetry, manifold).
    - Transformer model: algebra (attention, embedding) + geometry (positional encoding).
  - Difference between machine learning (deep learning) AlexNet and rule-based databases: exact matching vs. sampling.

  {{< /speaker_note >}}

---

### Multimodal Applications and Unified Embeddings {#multimodal-applications-and-unified-embeddings}

- Modalities:
  Language, image, video, audio.
- Embeddings
  - At a higher level of abstraction.
  - More efficient communication.
  - More efficient training/retrieval.
  - Encoding facts and common sense.
- No need for synchronized multimodal data, training can be done separately using images as a medium.
  - Generative models (understanding, mastering probability distributions, the basis for assumptions/reasoning).
  - The physics of information and intelligence.

{{< speaker_note >}}

- Embeddings at a higher level of abstraction.
- Reality is the ontology, only embeddings in perception (qualio, perception, sampling different modalities of reality samples).
- Asynchronous training: joint probability distribution is learned through individual marginal probabilities, interpolation.

  {{< /speaker_note >}}

---

#### Meta ImageBind {#meta-imagebind}

- Multimodal (image, text, audio, video, infrared imaging, IMU) joint supervised learning.
  - Training data does not need to be collected synchronously with all 6 modalities.
  - Training data samples can be collected asynchronously.
  - Performance far exceeds single-modality methods (image-based traditional methods and deep learning models).
- Generate photos of a rainforest or a farmers market from audio.
- Segment images based on sound/text (screaming to locate pedestrians in blind spots).

{{< speaker_note >}}

<https://imagebind.metademolab.com/demo>

{{< /speaker_note >}}

---

## Applications {#applications}

- Reasoning
  - Adapting to applications (prompt engineering).
  - Changing programming paradigms.
  - Application algorithm development.
- Adapting network models
  - SFT local modification and update.
  - Additional networks.
  - RLHF (Reward Model & PPO)
    - 👉 DPO (Direct Preference Optimization).
- Open source communities.

{{< speaker_note >}}

- Listed in ascending order of requirement/benefit/difficulty.
- Reasoning: Fundamental models as powerful oracles, but require the questioner to understand domain knowledge and context & understand the fundamental model.
  - Learn to ask questions, prompt engineering!
  - Construct chained reasoning questions.
  - Construct autonomous questioning agents.
- SFT: Improve the model.
- DPO: No need for reward models.
- Open source:
  - Meta, HuggingFace (TIMM), StabilityAI (Lucid Rains), Google, OpenAI, DeepMind, universities.
  - Principles, code, models.
  - Communicate with the smartest open source contributors in the world, 90% of developers are in the open source community.
- Algorithms: Increase sequence length; after Transformer, computational optimization (sparsification); attention improvement and alternative mechanisms.

  {{< /speaker_note >}}

---

### Shoggoth Model of Fundamental Model and Assistant Model {#shoggoth-model-of-fundamental-model-and-assistant-model}

{{< figure src="/ox-hugo/shoggoth.jpeg" alt="Shoggoth as LLM and RLHF" >}}

{{< speaker_note >}}

- Fundamental Model: GPT
- Assistant Model: ChatGPT

  {{< /speaker_note >}}

---

### Reasoning Applications {#reasoning-applications}

---

#### Technology Stack {#technology-stack}

- Web/App conversation interface.
- App/IDE plugins.
- Programmatic interfaces:
  - Front-end:
    - Standalone interface (Web: Flask, Streamlit), IDE, OA plugin interface, UI logic layer.
  - Back-end:
    - API interface (OpenAI, OpenPilot, Google Bard), vector database interface, algorithm logic layer: CoT/ToT/Agent/prompt template library/retrieval.

---

#### Prompt Engineering {#prompt-engineering}

- Sampling of neural networks.
- Fundamental model as a decoder.
- Database query.
- Overcoming the conversational length limitations of Transformer models (8~32k).
  - Constructing external long-term memory interfaces (vectorized databases) and processing logic (LangChain).
- Programmatic data adaptation pattern: Private data embedding, vectorized storage.
  - Database connection (LlamaIndex), data query.

{{< speaker_note >}}

- Predicting the next word, autoregressive iteration can process sentences and paragraphs. The essence is document completion, conditional probability.
  - Fundamental models (GPT3.5/GPT4, Palm2).
  - Assistant models (ChatGPT, Bard, LaMDA, OpenPilot): adapted to human conversation through SFT, RLHF.
- The most probable answer is not necessarily the optimal answer you want.
- Conditions are important! The structure of prompt engineering, adding conditions "Your IQ reaches 120 / You are a Python programming expert".
- Application programming interfaces, libraries are the best interfaces (formal languages).

  {{< /speaker_note >}}

---

#### Prompt Engineering Algorithms {#prompt-engineering-algorithms}

{{< figure src="/ox-hugo/tot.png" title="Latent Space Cluster Distribution" width="500pix" >}}

- Conversational format
  Input-Output Prompting.
- Chain of thought
  Chain-of-Thought.
- Tree of thought
  Tree-Of-Thought 👉 AlphaGo.

{{< speaker_note >}}

- Open the door to algorithms. Algorithmic module interface.

  {{< /speaker_note >}}

---

#### Autonomous Agents {#autonomous-agents}

- AutoGPT.
- BabyGPT.
- Programming paradigms worth paying attention to.

{{< speaker_note >}}

Not very useful in applications.
Not a problem of large models, but the automatic logic is too simple.

{{< /speaker_note >}}

---

### Customization {#customization}

---

#### Fine-tuning {#fine-tuning}

> Everyone should learn to fine-tune LLMs.
>
> ---Mark Tenenholtz

- GPT-4 is a frozen model.
- General purpose, but not optimal in specific domains.
- High overhead.
- Fundamental models are just decoders.
- Data is fundamental.

{{< speaker_note >}}

- Static, knowledge < 2021.09.
- Too general, not optimized for specific domains.
  - Adapting domain problems to fundamental models is like fitting a square peg into a round hole.
- Many applications don't need the generated parts, and many other areas don't need them.
  - Refining, reducing model size.
- Encoder-decoder is a more effective way of embedding refinement.
- Dataset maintenance and updates are very important.

  - Data quality.

  {{< /speaker_note >}}

---

#### Customizing Fundamental Models Based on Retrieval {#customizing-fundamental-models-based-on-retrieval}

- Enhanced retrieval based on customized vector databases.
- End-to-end retrieval augmented fundamental models.

{{< speaker_note >}}

- Based on vectorized databases.
- RAG (Retrieval Augmented Generation) P. Lewis, Meta end-to-end.

  {{< /speaker_note >}}

---

#### Training and Adaptation {#training-and-adaptation}

- Training fundamental large models "from scratch" (GPT4, Llama)
  - Large datasets.
  - OpenAI ~200 Engineers (Google 2000+).
  - Thousands of GPUs, months.
- Supervised adaptation training/efficient parameter adaptation training (SFT/PEFT)
  - Good small datasets.
  - 1-100 GPUs.
  - **LoRA training** 👉 QLoRA (2x4090, 24h@16bit).
  - LLM-Adaptor.
- Attention alternative algorithms
  - FlashAttention, State Space, RNN.

{{< speaker_note >}}

- Training fundamental large models is very expensive, and there may only be one or two companies doing it.
- Small models can outperform large models in specific domains.
- Adaptation is an active area of application.
- QLoRA (16 Bit, 48GB memory, 2x4090, 24h).
- Improving/replacing Attention is worth paying attention to.

  {{< /speaker_note >}}

---

#### Distillation and Adaptation (High-quality Data Acquisition) {#distillation-and-adaptation--high-quality-data-acquisition}

- Alpaca 7B
  - GPT3 Davinci-003 teaches LLaMA 7B.
  - 175 seed conversations --> 52,000 generated data --> SFT, <$500.
- Vicuna 13B
  - ChatGPT teaches LLaMA 13B.
  - 7 million conversation data (ChatGPT), @ 8xA100, 24h, ~$300.
- Koala 13B
  - ChatGPT & others teach LLaMA 13B.
  - ~41 million conversation data, @ 8xA100, 2 epochs, 6h, <$100.

{{< speaker_note >}}

- Alpaca 7B
  - Teacher: GPT3 Davinci-003 --> Student: LLaMA 7B.
  - 175 seed conversations --> 52,000 generated data --> SFT.
  - Cost: <$500.
- Vicuna 13B
  - Teacher: ChatGPT --> Student: LLaMA 13B.
  - 7 million conversation data (ChatGPT).
  - ~$300, @ 8xA100, 24h.
  - Evaluated by GPT4.
- Koala 13B
  - Teacher: ChatGPT & others --> Student: LLaMA 13B.
  - ShareGPT, Alpaca, Anthropic, OpenAI WebGPT & Summarization ~41 million.
  - @ 8xA100, 2 epochs, 6h, <$100.
- Guanaco 7B.
- MPT, OpenPilot.
- Red Pajama 1.2 trillion tokens.
- ShareGPT 30k+ HC3 24k + other open source dialogue datasets (OIG 30k + Alpaca 52k + Anthropic 160k + OpenAI WebGPT 20k + OpenAI Summarization 93k).

  {{< /speaker_note >}}

---

### Infrastructure {#infrastructure}

- Cloud (training & inference)
  - GCP, Azure, AWS, vector database API, search API.
- Mobile (inference).
- Software development
  - Front-end: Web (Flask, Streamlit), application plugins Slack/WeChat/DingTalk.
  - Large language model API interface (OpenAI, Bard).
- Local
  - Server, local vector database.
- Programming paradigms.

{{< speaker_note >}}

- Arjan OpenAI example
  - Start Jupyter server in terminal.
  - FrontEnd with StreamLit Example.
- LangChain Example
  - LANGCHAIN Jupyter notebook.
- pandas ai.

  {{< /speaker_note >}}

---

## Moats {#moats}

- Whether to proceed?
- How to proceed?
- How to judge whether it is too early to proceed and whether the investment is too large?
- Application reality?
  - How much profit?
  - Is the technology available?
  - Security?
  - What is the feasible cost of improvement?

{{< speaker_note >}}

Think about the situation at the beginning of the invention of electricity and automobiles.

{{< /speaker_note >}}

---

### Table and Text Analysis: {#table-and-text-analysis}

- OA documents, DingTalk, WeChat Work.
- Mini-programs, App customer data (table, text) analysis, summary, query.
  - Transaction behavior.
  - User preferences.

{{< speaker_note >}}

Manual verification, reduce workload.

{{< /speaker_note >}}

---

### Entertainment Systems (Natural Language Interface HMI, Systems, Software) {#entertainment-systems--natural-language-interface-hmi--systems--software}

- Requirements document generation (systems, software): natural language application interface.
- Hardware system design.
- System architecture design.
- Software requires human work:
  - Set up the development environment.
  - Manual verification (web api flask, embedded).
  - Programming paradigm changes.

{{< speaker_note >}}

- Manual verification, reduce workload.
- <https://hackaday.com/2023/05/22/chatgpt-rules-the-world-or-at-least-the-home/> (vehicle, audio, air conditioning, Bluetooth, body electronics (doors, windows), horn).
- Think about the knowledge required for the engineer's work in this case vs. the qualifications and knowledge of existing automotive system and software/hardware engineers.

  - If you don't know about hardware control, flask api, gpio:
  - Verification: Let GPT generate test cases.
  - Believe but verify! Need understanding, no need to remember! Architect.

  {{< /speaker_note >}}

---

### Intelligent Driving Projects {#intelligent-driving-projects}

- Segmentation: Occluded object analysis, completion.
- Target recognition: Automatic labeling of unknown targets.
- Single image 3D information reasoning (NERF + Google Street View large model).
- Prediction, planning.

---

### VEOS {#veos}

- Cloud model scaling.
- Multimodal grasp of application scenarios and driver styles.

---

### Time Series Fundamental Models {#time-series-fundamental-models}

- Methods: Chain/Tree Of Thought, Retrieval-based LLM, local modification.
- Control (behavioral feedback) fundamental models (reinforcement learning).
  - Active inference.
  - Embodied AI
    - The key to application and research.
  - Time series embedding, richer world model.
    - General intelligence distills objective physical laws.
    - Using embedded knowledge and laws to understand causality and spacetime.

---

### Conclusion {#conclusion}

- No algorithmic moat.
- Computing resource limitations are almost negligible.
- Data collection and collation.
- Operations, products, development integration.

> **Accept the new reality.**

{{< speaker_note >}}

- Whether the data is easy to search and query, easy to train.
- Basic understanding of algorithms (1-2 years, 10,000 hours).
- Exact structure, 96 coding layers, alternating traditional attention layers + sparse layers.
- Understanding technology: OpenAI, under GPT4.
- Large models
  - Training, debugging engineering (200 vs. 2000).
  - How to use.
- Where are the obstacles to applying fundamental models? 👉 Understanding.

  {{< /speaker_note >}}
