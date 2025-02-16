+++
title = "Game Theory, Optimal Control, and Machine Learning"
author = ["Xin Binjian"]
date = 2025-01-02T00:00:00+08:00
draft = false
+++

<div class="ox-hugo-toc toc">

<div class="heading">Table of Contents</div>

- [Objectives](#objectives)
- [A Simple Decision Problem](#a-simple-decision-problem)
- [Optimal Control, Reinforcement Learning, and Robotics](#optimal-control-reinforcement-learning-and-robotics)
- [Summary](#summary)

</div>
<!--endtoc-->

<div class="NOTES">

-   Rip Van Winkle, Washington Irving, 1819. Like a fleeting dream, missing the American Revolutionary War, a folk story from New York.

</div>


## Objectives {#objectives}

-   Common foundation of optimal control and machine learning
-   Programmatic approach to decision-making
-   Attaining optimal decisions through learning

<div class="NOTES">

-   Understanding reinforcement learning does not require understanding deep learning.
-   You can grasp the essence of deep learning from a reinforcement learning perspective.
-   The background and motivation of reinforcement learning itself occupy only a small portion.
-   Dark matter:
    -   Refers to basic facts often overlooked or subconsciously assumed—frequently incorrect assumptions—yet crucial for understanding issues.
-   Why does a robot grasping task use random decision-making? It’s counterintuitive!
    -   Combining logic and intuition to handle complex phenomena.
-   Fundamental questions can lead into the topic:
    -   Why use a tree structure?
    -   What is machine learning?

</div>


## A Simple Decision Problem {#a-simple-decision-problem}


### 1.1 Duel {#1-dot-1-duel}

> Game (Conflict)
>
> -   Elements of a game:
>     -   Players
>     -   Payoff (Cost, Reward)
>     -   Strategy
> -   The fun of the game: complexity, difficulty, balance

<div class="NOTES">

👉 Honor of Kings

</div>


#### Duel {#duel}

<div class="r-stack">
        <img class="fragment fade-out" data-fragment-index="0" src="img/drl101/dominated_fight_en.png" />
        <img class="fragment current-visible" data-fragment-index="0" src="img/drl101/dominated_fight0_en.png" />
        <img class="fragment current-visible" data-fragment-index="1" src="img/drl101/dominated_fight1_en.png" />
        <img class="fragment" data-fragment-index="2" src="img/drl101/dominated_fight2_en.png" />
</div>
<span class="fragment"; style="color:darkgreen; font-weight:bold"; data-fragment-index="2">Dominant Strategy</span>


### 1.2 Evenly Matched {#1-dot-2-evenly-matched}

<div class="r-stack">
        <img class="fragment fade-out data-fragment-index="0" src="img/drl101/ne_en.png" />
        <img class="fragment current-visible" data-fragment-index="0" src="img/drl101/ne1_en.png" />
        <img class="fragment current-visible" data-fragment-index="1" src="img/drl101/ne2_en.png" />
        <img class="fragment" data-fragment-index="2" src="img/drl101/ne3_en.png" />
        <img class="fragment" data-fragment-index="4" src="img/drl101/mixed1_en.png" style="height:400px" />
</div>
<span class="fragment"; style="color:darkgreen; font-weight:bold"; data-fragment-index="2">Strategy Equilibrium State</span>
<div class="fragment"; style="color:darkred; font-weight:bold"; data-fragment-index="3">?</div>

<div class="NOTES">

-   No dominant strategy.
    -   When certain problems have no answer, approaching them from another angle or level can reveal more intriguing phenomena or more important issues.
-   The overlap of strategies between rows and columns (two opponents) is the more crucial question.
    -   If one side chooses to attack while the other side retreats, neither side wants to deviate from this state—this is the equilibrium (Nash equilibrium).

</div>

<div class="NOTES">

-   The premise is that both sides decide simultaneously and do not know each other’s strategy!
-   Strategy equilibrium is bounded by a stable, balanced state.
-   A strategy equilibrium is most reasonable and optimal for both sides: if any party deviates from the equilibrium and the other side keeps rational decisions, the deviating side’s payoff suffers, so no one wants to deviate from the optimal decision within this equilibrium.
-   A’s irrational decision vs. B’s rational decision.
-   Rational decisions are better than irrational ones.
-   How many equilibrium states are there?

</div>


### 1.3 Mixed Strategy {#1-dot-3-mixed-strategy}

<a id="figure--Mixed Strategy"></a>

{{< figure src="/ox-hugo/mixed1_en.png" title="Mixed Strategy" width="300px" >}}

-   Opponent’s Attack Payoff: \\(\color{red}{PO^{f}=(-1)\times p^{A} + (2)\times (1-p^{A})}\\)
-   Opponent’s Retreat Payoff: \\(\color{blue}{PO^{q}=(0)\times p^{A} + (0)\times (1-p^{A})}\\)
-   \\(p^{A}=0.5\\) ?
-   When is \\(p^A\\) optimal?

    👉 Force the opponent into no choice, valid for \\(\forall\hspace{0.5em}p^{B}\\)

    <div class="NOTES">

    -   Our payoff is -0.5 : 1
    -   Opponent’s payoff is 0.5 : 0
    -   Our payoff depends on the opponent’s decision!
    -   Regardless of the opponent’s strategy, the payoff is the same.

    </div>


#### Mixed Strategy {#mixed-strategy}

{{< figure src="/ox-hugo/mixed1_en.png" title="Mixed Strategy" width="300px" >}}

-   Our strategy: \\(\color{red}{PO^{f}}=\color{blue}{PO^{q}}\\) 👉 \\(p^{A}=\frac{2}{1+2}=\frac{2}{3}\\)
    -   Payoff?
    -   \\(p^{A}=1\\)?
-   Rational decisions are better than irrational decisions

    <div class="NOTES">

    -   Equilibrium strategy: our payoff is \\(-\frac{2}{3}\times p^{B} + \frac{4}{3}\times (1-p^{B})\\)
    -   A’s irrational decision (p=1,0.5) vs. B’s rational decision (p=2/3)

    </div>
-   The equilibrium of a mixed strategy most reasonable and optimal

    <div class="NOTES">

    -   In a mixed-strategy equilibrium, if either side deviates while the other side remains rational, the deviating side’s payoff decreases. Hence no one wants to deviate from the equilibrium’s optimal decision.

    </div>
-   A random strategy is superior to a deterministic one

    <div class="NOTES">

    -   Randomness is an efficient model for dealing with complex phenomena.
    -   How do we choose an optimal strategy from random strategies? We compute the probability distribution of signals to find the optimal strategy matching our goals.

    </div>


#### Mixed Strategy {#mixed-strategy}

{{< figure src="/ox-hugo/mixed1_en.png" title="Mixed Strategy width 300px" >}}

-   Ongoing repeated showdown?


### 1.4 Over the River of Time {#1-dot-4-over-the-river-of-time}


#### Decision Tree {#decision-tree}

<div class="r-stack">
 <img class="fragment fade-out data-fragment-index="0" src="img/drl101/mixed1_en.png" />
 <img class="fragment current-visible" data-fragment-index="0" src="img/drl101/flat_tree.png" />
 <img class="fragment" data-fragment-index="1" src="img/drl101/flat_tree2.png" />
</div>

<div class="r-stack">
 <img class="fragment fade-out data-fragment-index="2" src="img/drl101/tree.png" />
 <img class="fragment" data-fragment-index="2" src="img/drl101/flat_tree3.png" />
</div>

<div class="NOTES">

-   Decision trees are almost the only model for decision theory (reinforcement learning).
-   Crucial for understanding time-series.

</div>


### 1.5 Continuous Showdown {#1-dot-5-continuous-showdown}

<div class="r-stack">
        <img class="fragment fade-out data-fragment-index="0" src="img/drl101/tree21.png" />
        <img class="fragment current-visible" data-fragment-index="0" src="img/drl101/tree3.png" />
        <img class="fragment" data-fragment-index="1" src="img/drl101/tree4.png" />
</div>

-   Work backward step by step: analyze starting from the last round
-   Probability of attack \\(\mathcal{P}=\frac{v}{v+c}: \frac{2}{3}\searrow 0,\ \textrm{if}\ v:2\searrow 0\\)
-   Value function: the long-term value of the current decision and state

<div class="NOTES">

-   The complexity of time series increases exponentially!
-   Biological evolution is also tree-structured.
-   The branching evolution of cause-and-effect sequences.

</div>

<div class="NOTES">

-   Optimal decisions must account for the long-term consequences of short-term actions.
    -   There is a fundamental principle (akin to basic physical laws) allowing quick assessment of the long-term consequences of short-term actions:
        -   Natural world, accumulated experience.
        -   Optimal control, reinforcement learning.
-   How do we evaluate these consequences?
    -   Approach it like accumulated experience, building up a “value function.”

</div>


## Optimal Control, Reinforcement Learning, and Robotics {#optimal-control-reinforcement-learning-and-robotics}


### 2.1 Review {#2-dot-1-review}


#### Ten Years Ago {#ten-years-ago}

<div class="NOTES">

-   PR2
    -   In 2010, Willow Garage (ROS, Andrew Ng)
    -   Actuators, sensors (depth camera, lidar), body, joints
    -   Costs are going down
    -   Body is more bionic (more complex)
-   Asimo
    -   Difference between gait control and modern robots
    -   Current reference: <https://www.youtube.com/watch?v=6CjxMPg0pvg>

</div>


#### Optimal Control {#optimal-control}

<div class="NOTES">

2019 talk

-   Early control theory: PID feedback control, linear control; assumes linear systems, simple and elegant
    -   Unspecific application to other control targets led to complex expert systems and complicated engineering projects
    -   Feedback control theory: zero-pole compensation → cancels the system’s original dynamics, not using the system’s own dynamics
-   1990s, 12:45: Optimal control (approximate dynamic programming) vs. reinforcement learning
    -   The main difference is that RL emphasizes interaction with the environment, learning-based
    -   Optimal control (approximate dynamic programming, adaptive control, robust control) focuses on system identification and model approximations
    -   Shallow neural networks, no deep learning
    -   Dimitri P. Bertsekas
-   14m18s~15m57s;
-   Will briefly comment on AlphaGo’s algorithm

</div>


#### Reinforcement Learning {#reinforcement-learning}

{{< figure src="/ox-hugo/jim_fan.png" title="Year_Of_RL width 400px" >}}

{{< figure src="/ox-hugo/deepseek_r1_arxiv.png" title="R1 width 400px" >}}


### 2.2 Model {#2-dot-2-model}

<div class="ox-hugo-table noboldheader">

| Game/Conflict                                                                                             | Players                                                                                             | Payoff <br>(Cost)                                                                         | Strategy                                                                                       | State                                                                                    | Strategy Evaluation                                                                               |
|-----------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
|  <span class="fragment" data-fragment-index="1"><font color=darkblue>Reinforcement Learning</font></span> |  <span class="fragment" data-fragment-index="1"><font color=darkblue>Agent/<br>System</font></span> |  <span class="fragment" data-fragment-index="1"><font color=darkblue>Reward</font></span> |  <span class="fragment" data-fragment-index="1"><font color=darkblue>Action</font></span>      |  <span class="fragment" data-fragment-index="1"><font color=darkblue>State</font></span> |  <span class="fragment" data-fragment-index="1"><font color=darkblue>Value Function</font></span> |
|  <span class="fragment" data-fragment-index="2"><font color=red>Optimal Control</font></span>             |  <span class="fragment" data-fragment-index="2"><font color=red>Controller/<br>Object</font></span> |  <span class="fragment" data-fragment-index="2"><font color=red>Error</font></span>       |  <span class="fragment" data-fragment-index="2"><font color=red>Control Variable</font></span> |  <span class="fragment" data-fragment-index="2"><font color=red>State</font></span>      |  <span class="fragment" data-fragment-index="2"><font color=red>Objective Function</font></span>  |

</div>

<div class="NOTES">

-   Players: humans vs. humans, computers, nature/physical laws;
-   Computer vs. nature/physical laws
-   Adding observations and value estimates
    -   In reinforcement learning, the value function is learned and depends on the system state and actions, taking into account system equations and dynamics
    -   In optimal control, the objective function is based on expert rules and doesn’t consider system dynamics!

</div>

<a id="figure--Reinforcement Learning Model"></a>

{{< figure src="/ox-hugo/rl_model_en.png" title="Reinforcement Learning Model" width="750pix" >}}


### 2.3 Methods in Reinforcement Learning {#2-dot-3-methods-in-reinforcement-learning}

> Solve complex problems step by step

-   "Given the present, the future is independent of the past"

    👉 Markov Decision Process
-   Complex problems can be decomposed into subproblems

    👉 Dynamic Programming
-   Estimate the values of states and actions from fragmented experiences

    👉 Bellman Equation

<div class="NOTES">

-   Understanding the concept is more important than memorizing its name
-   Dynamic programming is the mainstream classical concept and the foundation of optimal control
-   The shortest path from A to B can be divided into two stages, A to C and C to B: if the path from C to B is shortest, then you only need to solve the subproblem from A to C!

</div>


#### Rational Decision Making {#rational-decision-making}

> -   Algorithms embody rational decision making
> -   Rational decisions serve as a counterstrategy against irrational decisions

<div class="NOTES">

-   AlphaGo is very hard to beat; humans are hard to beat by machines: perfect memory, pure rationality, efficient execution, and replicable behavior
-   There is no predetermined purpose
-   Jeff Hinton’s warning
-   Originally, reinforcement learning was a relatively obscure area in AI; its biggest difference from optimal control is the incorporation of learning.
    -   Why has it become mainstream in AI and robotics since 2016? --&gt; Deep Learning.
    -   How to combine the two? Sampling! Learning from fragmented experiences.

</div>


### 2.4 Learning from Fragmented Experiences {#2-dot-4-learning-from-fragmented-experiences}


#### Random Sampling {#random-sampling}

<div class="r-stack">
        <img class="fragment fade-out" data-fragment-index="0" src="img/drl101/tree_sample0.png" />
        <img class="fragment current-visible" data-fragment-index="0" src="img/drl101/tree_sample.png" />
        <img class="fragment current-visible" data-fragment-index="1" src="img/drl101/tree_sample1.png" />
        <img class="fragment current-visible" data-fragment-index="2" src="img/drl101/tree_sample2.png" />
        <img class="fragment" data-fragment-index="3" src="img/drl101/tree_sample3.png" />
</div>


#### Advantages of Random Sampling {#advantages-of-random-sampling}

<a id="figure--Random Decision Sampling"></a>

{{< figure src="/ox-hugo/tree_sample1.png" title="Random Decision Sampling" width="500pix" >}}

-   Real data
    -   Modeling complexity is too high
-   Complex functions/distributions:
    -   Nonlinear
    -   Time-varying and non-stationary processes
-   Natural laws
-   An efficient way to tackle complex problems
-   Allows learning from fragmented experiences

<div class="NOTES">

-   Rolling dice is often the most efficient learning method in complex, random environments
-   Deterministic mathematical problems can often be solved in an elegant and efficient way using probabilistic methods (combinatorics)

</div>


#### Optimal Control vs. Reinforcement Learning {#optimal-control-vs-dot-reinforcement-learning}

<div class="r-stack">
   <img class="fragment" data-fragment-index="0" src="img/drl101/hiking.jpg" height="400px"/>
</div>
<div class="r-stack">
   <div class="centered"><span class="fragment" data-fragment-index="0">Optimal Control</span></div>
</div>

<div class="r-stack">
   <img class="fragment current-visible" data-fragment-index="1" src="img/drl101/surfing.jpg" height="400px"/>
   <img class="fragment" data-fragment-index="2" src="img/drl101/skateboarding.jpg" height="400px"/>
</div>
<div class="r-stack">
   <div class="centered"><span class="fragment current-visible" data-fragment-index="1">Reinforcement Learning</span></div>
   <div class="centered"><span class="fragment" data-fragment-index="2">Robot Reinforcement Learning</span></div>
</div>


### 2.5 Model Complexity {#2-dot-5-model-complexity}


#### AlphaGo’s State and Decision Tree {#alphago-s-state-and-decision-tree}

<a id="figure--AlphaGo Decision Tree"></a>

{{< figure src="/ox-hugo/MCTS-in-AlphaGo.png" title="AlphaGo Decision Tree" width="800pix" >}}

-   Value: can be interpreted as the win rate


#### AlphaGo’s State and Decision Tree {#alphago-s-state-and-decision-tree}

<a id="figure--AlphaGo Decision Tree"></a>

{{< figure src="/ox-hugo/alphago_mcts.png" title="AlphaGo Decision Tree" width="800pix" >}}


#### AlphaGo’s Complexity {#alphago-s-complexity}

-   All positions (observations): \\(3^{{19}^2}\approx 1.74\times 10^{172}\\), with \\(1.20\\%\\) legal moves
-   Approximately ~200 moves per game, with an average of ~\\(3\times 10^{511}\\) different games
-   Theoretically, the maximum number of moves is \\(10^{48}\\), with the number of different games ranging from \\(10^{10^{48}}\\) to \\(10^{10^{171}}\\)
-   Number of atoms in the observable universe: \\(10^{80}\\)

    👉  Neural Networks

<div class="NOTES">

-   Number of atoms: Eddington number
-   Learning from complete but partial experience: learning from fragments of games and accumulating experience
-   Learning from incomplete experience: online learning, where learning happens concurrently with gameplay
-   It has been solved—a truly awe-inspiring achievement!
    -   A summary of human wisdom and experience: offense and defense, formations, life-and-death, endgame, coordination, overall situation, techniques, and tactics
    -   Efforts to summarize human experience using feature methods cannot compete with AlphaGo
-   The bitter lessons of artificial intelligence

</div>


#### The State and Complexity of a Bipedal Robot {#the-state-and-complexity-of-a-bipedal-robot}

<div class="NOTES">

-   Another example of embodied intelligence: Cassie, a bipedal robot
-   5m57s~6m27s, 7m08s~8:45s:
    -   Inertia/mass matrix is positive definite, exhibiting high complexity
    -   The system’s state and dynamics, and the policy (controller)
    -   Objectives (payoff, control trajectory) and strategy evaluation (player)
-   Complexity:
    -   Dynamic systems with long-term influence of control variables
    -   Partial observability/randomness
    -   Nonlinearity
    -   Legged robots are underactuated systems,
        -   Deliberately so; they are harder to control but more natural and energy-efficient. A natural gait is the optimal control solution—moving with minimal energy in an economical manner (the way control variables affect state variables)!

</div>

-   Methods for controlling complex objects:

    -   Optimal control

        <div class="NOTES">

        -   Lagrangian mechanics: force/torque → action; the time integral of energy (kinetic and potential) changes; force/energy variations produce motion
        -   Principle of steady-state action (motion follows energy equilibrium, conservation): every system’s dynamics follows a unique path
        -   Since the 1990s, two approaches have emerged
        -   There is no simple, magical method for handling complex phenomena—it requires significant computational resources and the key is how to apply them: either for system identification or for stepwise digestion of fragmented experience data
        -   Optimal control, via approximate dynamic programming (Approximate DP): it uses precise environmental and dynamic models to capture the primary contradictions; however, its drawbacks include specificity to the model, being tailored for particular scenarios (difficult to generalize), and poor robustness against disturbances

        </div>

    <!--listend-->

    -   Reinforcement learning

        <div class="NOTES">

        -   Uses random and probabilistic models to learn in a manner similar to how nature and humans solve problems
        -   The system’s state and policy are obtained through learning
        -   Why is reinforcement learning effective in handling complex problems?

        </div>
-   How to learn?

    <div class="NOTES">

    -   Primarily due to breakthroughs in deep learning
    -   In practice, complex system dynamics are learned from fragmented experiences
    -   Evaluation of complex value functions and policies is achieved!

    </div>


### 2.6 Machine Learning for Robotics {#2-dot-6-machine-learning-for-robotics}

-   Each demonstration is a path on the decision tree
-   Data density obtained through random sampling
-   Experiences of success and failure

<div class="NOTES">

-   Reinforcement learning training
-   Covering observation data distributions specific to functionalities
-   Paths representing success or failure

</div>


#### The Role of Simulation {#the-role-of-simulation}

<a id="figure--pick"></a>

{{< figure src="https://developer-blogs.nvidia.com/wp-content/uploads/2022/07/image16.gif" caption="<span class=\"figure-number\">Figure 1: </span>Grasp" width="400pix" >}}

<a id="figure--position"></a>

{{< figure src="https://developer-blogs.nvidia.com/wp-content/uploads/2022/07/image5-1.gif" caption="<span class=\"figure-number\">Figure 2: </span>Position" title="tree" width="400pix" >}}

<a id="figure--operation"></a>

{{< figure src="https://developer-blogs.nvidia.com/wp-content/uploads/2022/07/image6.gif" caption="<span class=\"figure-number\">Figure 3: </span>Operation" title="tree" width="400pix" >}}


#### Simulation Data for Training {#simulation-data-for-training}

<div class="NOTES">

-   15:24 ~ 16:57
-   ACRONYM: Nvidia FLEX
-   Imagine describing it in a modeling framework
-   Skill requirements for application engineers: may not necessarily include programming

</div>


#### Algorithms for Robot Learning {#algorithms-for-robot-learning}

-   Data
    -   Sources: online/offline/(simulation)
    -   Pre-training (foundation models such as GPT)
    -   Data paradigms (training planning/data/diversity construction)
-   Learning Models
    -   Robustness
    -   Diversity

<div class="NOTES">

-   Learning models: representational learning, neural networks
-   Data is extremely important
    -   Online/offline
    -   Pre-training (foundation models like GPT)
        -   The foundation model provides common sense and fundamental reasoning ability; cross-domain learning (e.g., autonomous driving experience can benefit humanoid robotics performance)
    -   Data diversity is crucial; multimodal robot data is more significant: training the same model can improve average performance by over 50%
-   Efficient learning models can capture complex behavioral patterns (multimodal)

</div>


### 2.7 Understanding AlphaGo {#2-dot-7-understanding-alphago}


#### AlphaGo System Architecture {#alphago-system-architecture}

<a id="figure--AlphaGo Neural Network"></a>

{{< figure src="/ox-hugo/alphago_nn.png" title="AlphaGo Neural Network" width="600pix" >}}

-   Learning from fragmented experiences
    -   Accumulation of partial experiences
        -   👉 Neural Networks
    -   Aggregation of incomplete experiences
        -   👉 Online Learning
-   Randomness and probability are effective models for addressing complexity
    -   Value network: a simple win-rate lookup table

<div class="NOTES">

-   One can complete a game and then learn from it
-   It is possible to learn while playing (temporal difference learning)
-   Decision network,
-   Although the complexity of Go is extremely high, it is a deterministic game

</div>


#### Optimal Strategy {#optimal-strategy}

<a id="figure--AlphaGo Neural Network"></a>

{{< figure src="/ox-hugo/alphago_nn.png" title="AlphaGo Neural Network" width="800pix" >}}

-   Equilibrium Strategy
    -   The equilibrium of mixed strategies represents the most optimal and reasonable state for both sides
    -   Rational decision making outperforms irrational decision making
-   Self-training / Self-learning
    -   Equilibrium State (Optimal Strategy)

<div class="NOTES">

-   Why is the equilibrium strategy optimal?
    -   In a mixed-strategy equilibrium, if one side deviates while the other maintains rationality, the deviating side’s payoff will decrease—thus, no side has an incentive to deviate from the optimal decision under equilibrium.
    -   Intuition: Establishing an invincible defense before attacking the opponent
-   A’s irrational decision (human players) vs. B’s rational decision (AlphaGo)
-   Nash Equilibrium: In self-play, my decision must render the opponent’s payoff identical regardless of their choice
    -   Self-training / self-learning: a dual-combat process
    -   Why self-training leads to improvement:
        -   Mathematically: under reasonable assumptions (payoff &gt; cost, v &gt; c), a rational decision implies that at equilibrium, the first derivative of the payoff is zero and the second derivative is negative.

</div>


## Summary {#summary}

-   Optimal Strategy
    -   Optimal decision making must consider the opponent's decisions
-   Machine Learning
    -   <span class="r-stack">
        <span class="fragment fade-out"; data-fragment-index="4">Random sampling is an efficient method for tackling complex problems</span>
        <span class="fragment fade-in"; style="color:#FF0000; font-weight:bold"; data-fragment-index="4">Random sampling is an efficient method for tackling complex problems</span>
        </span>
-   Neural Networks
    -   Randomness and probability are effective models for addressing complex phenomena
