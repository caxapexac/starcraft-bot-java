# Поиск и сравнение аналогов

## Macro

### Use of Machine Learning Techniques in Real-Time Strategy Games
- 2018
- <https://ieeexplore.ieee.org/abstract/document/8490528>
- [[docs/certicky2018.pdf]]
- Тупо детектят текущую макро стратегию противника
- Обучали на bot vs bot. 3000 реплеев
- BWAPI
- Algorithm: ??? (Binary classification on replay data using cross-validation technique)
	- creating a dataset of atypical strategies which are often overlooked and using machine learning methods for detection of these strategies during the gameplay
	- Binary classification models were trained to detect each particular strategy and evaluated in a set of replay data using cross-validation technique
	- training of a set of binary classification models on top of the obtained from the replays
	- When expanding the model to the new strategies, such approach presents more flexible solution, as it is not needed to re-train and re-deploy the model (only a new model for particular strategy will be added).

### Investigation of the Effect of “Fog of War” in the Prediction of StarCraft Strategy Using Machine Learning
- 2016
- <https://dl.acm.org/doi/abs/10.1145/2735384>
- [[docs/2735384.pdf]]
- BWAPI
- реплеи human vs. human, human vs. AI bots, and AI bots vs. AI bots
- Детектят одну из трёх макро стратегий протосов, зная не всю инфу из-за тумана войны
- Algorithm: Random Forest, NNGE, MLP (Multi-Layer Perceptron), KNN
	- Считают количество зданий по логам игры без тумана войны
	- Because there are three race types in StarCraft, there are six possible types of game. However, we focus on Protoss vs. Protoss
	- We categorized the opponent strategy into three categories that gamers usually refer as “Three Gateway,” “Observer,” and “Dark Templar.”

### Behaviour oriented design for real-time-strategy games: An approach on iterative development for STARCRAFT AI
- 2013
- <https://researchportal.bath.ac.uk/en/publications/behaviour-oriented-design-for-real-time-strategy-games-an-approac>
- [[GaudlFDG13.pdf]]
- Algorithm: Behaviour Oriented Design (BOD)
	- FSM им не понравился, потому что не умеет планировать и предсказывать
	- Potential fields хвалят, говорят есть успешные результаты. There are also approaches covering evolutionary multi-agent potential fields (EMAPF)
	- A more general-purpose type of machine learning approach called reinforcement learning has been used for developing StarCraft AI, and has been proven to be effective way to control groups of units. However, all forms of machine learning still require careful design in order to reduce the combinatorial possibilities of the behaviour to be learned to something tractable. This fact is sometimes overlooked or underreported in the description of the algorithms.
	- Monte Carlo Tree Search (MCTS) have seen recent success in games like Go and even in games with incomplete information such as Magic: The Gathering. The main diculty when trying to use search in StarCraft is, as with machine learning, the search space is too big
	- Goal-Driven Autonomy. This approach was found to be useful for the high level strategies in StarCraft, where the system would have an overall plan
	- Behaviour-Based Artificial Intelligence. This approach adds modularity to a FSM system, by having multiple finite state machines each specialised to a sub task of the problem and thus easier to program. much more scalable to large systems compared to a basic FSM. However, later BBAI used other representations for the modules than FSM, including potential fields
	- Behaviour Oriented Design (BOD). AI development methodology that combines an iterative development process based around variable state for learning and planning with the modular, responsive architecture of BBAI. Не очень понял отличия от behaviour tree
	- Behaviour Trees. Ну обычные академические BT

### Adaptive High-level Strategy Learning in starcraft
- 2013
- [[03-full-paper.pdf]]
- <http://www.sbgames.org/sbgames2013/proceedings/comp/03-full-paper.pdf> не смог найти источника
- BWAPI
- Только терраны, 5 видов стратегий
- Algorithm: reinforcement learning + Q learning? + e-greedy?
	 - uses (RL) reinforcement learning (a learning algorithm that only looks at the rewards and punishments for actions in the game state)
	- main goal is to create a learning algorithm for StarCraft that knows how to switch strategies between opponents and pick an optimal strategy that is based on RL learning.
	- determines when an opponent changes strategy and stores multiple sets of RL data to combat recognized strategies.
	- Uses a mechanism called e-greedy. Has a possibility to select a random action rather than optimal known action to explore unknown states.
	- uses meta-learning to attempt to improve its own ability to learn
	- Base for AI was bot BTHAI
	- Only played Terran and focuses on 5 strategy or sets of RL data.
	- played against variable AI bot (only terran and protos but varying preset strategies (rush defensive ect) on only one map (fading realm) played 138 matches
	- Bot used a Q value to determine if it needed to learn more of less and this varied wildly depending on the opponent it was facing but overtime approached 0
	- overall успешно достигли цели


### A Competitive Combat Strategy and Tactics in RTS Games AI and StarCraft
- 2018
- [[docs/978-3-319-77383-4_1.pdf]]
- <https://link.springer.com/chapter/10.1007/978-3-319-77383-4_1>
- Algorithm: Тупо plot and decision tree для создания соревновательного AI
	- Used reruns and replays to base it off of.
	- Не осилил победить базовый AI 

### Opponent Modeling and Strategic Reasoning in the Real-time Strategy Game Starcraft
- 2012
- <https://ntnuopen.ntnu.no/ntnu-xmlui/handle/11250/252930>
- [[docs/565941_FULLTEXT01.pdf]] (99 страниц и половина на швецком)
- BWAPI
- Algorithm: decision tree
	- Goal is to build an AI that can recognize the strategy of the opponent and selecting a strategy that is capable of countering it.
	- uses replays from the game to gather data and create decision trees based on what other players did. More replays means more information meaning better bot.  
	- uses a noise perimeter to determine how inaccurate the predictions are as without total knowledge of the game state the AI is only making its best guess as to the opponents build.
	- Более успешен в начале чем в конце из-за увеличения вариативности. Но довольно успешен против базового AI

### Prediction of Early Stage Opponents Strategy for StarCraft AI using Scouting and Machine Learning
- 2012
- [[2425296.2425298.pdf]]
- <https://dl.acm.org/doi/abs/10.1145/2425296.2425298>
- BWAPI
- Определяют стратегию через скаутинг юнитом ездящим по радиусу вокруг базы
- Algorithm: 13 алгоритмов - They’re categorized into rules (ZeroR and oneR), decision tree (J48, Cart, Decision Stump and Random Forest), lazy learning (1-NN, and NNge), neural networks (MLP), probabilistic models (Bayesian Network and Nave Bayes), and SVM. Because the number of samples is small, LOOCV (Leave-One-OutCross Validation) is used. For each classiﬁer, default parameters in WEKA are used.
	- goal is to create a machine learning algorithm to predict an opponent’s attack strategy (early or late game) using early game scouting.
	- Data collected between matches between the bot and human players.
	- is improving previous decision tree based bot to better know which counter to use earlier in the game by predicting an initial strategy.
	- played 105 games for learning with the AI vs random humans on a public server
	- the actual scouting was not machine learning only determining what the opponents strategy is. The scouting was done by having the scout circle around buildings at a set distance attempting to circle as many as possible before death. This ignores opponent units and considers all buildings the same.

### Macromanagement and Strategy Classiﬁcation in Real-Time Strategy Games
- 2019
- [[docs/CCHI.2019.8901957.pdf]]
- <https://ieeexplore.ieee.org/abstract/document/8901957>
- BWAPI
- Определяют макро стратегию противника
- 240 реплеев Протоссов
- Algorithm: HMM (Hidden Markov Model), a statistical model, which is used to describe a Markov process with hidden unknown parameters. Baum-Welch algorithm to learn the HMM parameters and train 9 different HMM models. KNN (k-nearest neighbors ) in strategies where HMM is too simple. KNN is better at sensitive strategy classification such in cases where two are very similar or very complex. KNN tended to do better then HMM
	- Работает но зависает если не понимает что происходит
	- Внешне выглядит как обычное дерево решений, просто чуть больше переменных


### Building Behavior Trees from Observations in Real-Time Strategy Games
- 2015
- [[docs/inista.2015.7276774.pdf]]
- <https://ieeexplore.ieee.org/abstract/document/7276774>
- Algorithm: Gapped Local Alignment of Motifs (GLAM2)
	- goal is to make a good behavior tree (basically and if or flow chart) without any additional information. So no reward or action models, just trying to make an optimal flow chart without reactions.
	- attempting to make an automated system make one off of replays that a human can then edit.
	- restricts the system to a single end goal
	- the way it works is it takes replay actions and then condenses them based on repetition to make a shorter and repeated flow chart (basically instead of make scv 20 times as separate actions it turns it into make scv until scv’s reach 20.
	- 389 replays condensed 218832 decisions into 71294
	- Не тестили потому что не нашли бота под микроменеджмент


### Predicting Opponent’s Production in Real-Time Strategy Games with Answer Set Programming
- 2013
- [[docs/TCIAIG.2014.2365414.pdf]]
- <https://ieeexplore.ieee.org/abstract/document/6936913>
- BWAPI
- 555 реплеев
- Algorithm: ASP solver classed CLASP, околодекларативное программирование
	- goal is to discover what build order/strategy the opponent is using
	- uses answer set programming. Basically it predicts with limited information using the knowledge about the rules and common builds in the game. Looks for specific preset answer sets(so build order in this case) based on the information it gathers in game. (a good example is if it sees 12 zelots within 200 seconds of game start it, it will know that the opponent has 3 gateways and can infer from there)
	- uses a ASP solver classed CLASP to gather data from the game for the bot
	- Успех 68%

## Resource production

### Resource-Gathering Algorithms in the Game of StarCraft 
- 2017
- [[docs/CIG.2017.8080445.pdf]]
- <https://ieeexplore.ieee.org/abstract/document/8080445>
- Улучшение дефолтного алгоритма сбора ресурсов
- Algorithm: 5 algorithms are Built-in (III-A), Mineral-lock (III-B), Queue Based Scheduling (III-C), Co-operative pathﬁnding (III-D), and Co-operative pathﬁnding + Queue (III-E).
	- focuses on creating 5 algorithms for improved resource gathering efficiency 
	- the builtin algorithm for resource gathering is not optimal in the game so they intend to create this to surpass it.
	- built in uses the default gathering except if a mineral is full it will move a worker to a new one.
	- Mineral lock evenly distributed workers on all mineral fields. Reassigns workers as minerals are freed up.
	- Queue based scheduling. Created a Queue for each mineral and the algorithm determines the optimal worker queue
	- co-oporative pathfinding. The default worker pathfinding is not optimal for mining this micromanages them to be optimal
	- and Co-operative pathﬁnding + Queue. Uses both to create a faster and most efficient mining setup but is very demanding on CPU.
	- on average Co-operative pathﬁnding + Queue gathers 14% more minerals then the default.

### Maximization of the Resource Production in RTS Games using Planning and Scheduling
- 2013
- [[docs/ICA2938.pdf]]
- <https://www.semanticscholar.org/paper/Maximization-of-the-Resource-Production-in-RTS-and-Naves-Lopes/8473a5eaeb9b65550aef58f9d5599efe18c11131>
- Algorithm: Simulated Annealing + planning and scheduling
	- goal is to maximize resource production using planning and scheduling of workers  
	- uses a planner system (basically a flow chart) to determine plan order fairly simplistic like goal is to create firebat in 160 seconds the system determines the most efficient way to do that while maximizing resource gain.
	- The scheduling system or algorithm 2 is what looks to create the most resource efficient way to make the firebat. No machine learning just finds the most efficient method given the inputs.
	- tested in 20 runs was generally worse than a regular player at gathering resources and achieving a goal in specific timeframe.


### Maximization of the Resource Production in RTS Games through Stochastic Search and Planning
- 2012
- [[docs/icsmc.2012.6378074.pdf]]
- <https://ieeexplore.ieee.org/abstract/document/6378074>
- prequel to previous paper
- Algorithm: Simulated Annealing + stochastic search and planning
	- goal is to maximize gathering resources and army power  
	- creates a sequential planner based on the STRIPS language
	- Is intending to achieve one goal as efficiently as possible generally making the plan backbone to the upgrade in the 2013 paper it is mostly a flowchart design that the algorithm makes more efficient
	- tested in 20 runs was generally equal to a player and was actually better then their 2013 version.

### Resource Production in StarCraft Based on Local Search and Planning
- 2017
- [[naves2017.pdf]]
- <https://link.springer.com/chapter/10.1007/978-3-319-62392-4_7>
- Algorithm: SA (simulated annealing) algorithm, POPlan, (partial order planning) a scheduler which bulds the plan that the SA uses, and SHELRChecker which validates plans to be effective.
	- goal is to maximize real-time resource production in the early game before conflict
	- found that breaking up the goals in 300 second intervals was most successful
	- Tested against human player and open source bots. Was relatively even with player and surpassed Bot.  
	- is not machine learning and did not use data sets from replays or anything just game mechanics and the POPlan bot decided best course of action based on situation but did not learn over time.
	- Лучше чем предыдущие статьи про resource production в этом списке

## Build order

### Build Order Optimization in StarCraft
- 2011
- <https://www.aaai.org/ocs/index.php/AIIDE/AIIDE11/paper/viewPaper/4078>
- [[docs/4078-17622-1-PB.pdf]]
- BWAPI
- Algorithm: DFS with some heuristics


###  Robust Continuous Build-Order Optimization in StarCraft 
- 2019
- [[docs/CIG.2019.8848109.pdf]]
- <https://ieeexplore.ieee.org/abstract/document/8848109>
- BOSS (Build-order search system an open source software project and part of the UAlbertaBot StarCraft AI agent)
- Algorithm: Просто поиск по дереву с эвристиками?
	- Intends to build a system that replaces human macro planning of build orders in AI development. Replacing all static systems with something more adaptable and less hand crafted.
	- uses heuristic search to abstract concepts such as ﬁrepower maximization rather than focusing unit count goals or build count goals.
	- main flaw is it looks at a specific time to accomplish its goals and thus is late in building a military leading to rush builds or the same AI set to a shorter timeframe easily beating it.
	- mainly is intending to be a useful algorithm for a larger future AI system.
	- ran 50 tests against another AI bot that has won tournaments the BOSS system won about 35% VS default StarCraft AI in 1500 games it won 1494 of them.


## Micro

 ### Neuroevolution for Micromanagement in the Real-Time Strategy Game Starcraft: Brood War
 - 2013
- <https://link.springer.com/chapter/10.1007/978-3-319-03680-9_28>
- [[docs/zhen2013.pdf]]
- BWAPI
- Algorithm: NEAT, rtNEAT
	- The NeuroEvolution of Augmented Topologies (NEAT) algorithm, both in its standard form and its real-time variant (rtNEAT) is comparatively evaluated in micromanagement tasks
	- analyzed the difference in performance between standard NEAT and the real-time variant, both in the rate of learning and in match performance
	- Neuroevolution (NE) has shown effectiveness compared to standard RL, in problems with continuous and high-dimensional state spaces
	- NEAT evolution after match
	- rtNEAT evolution every n ticks (50)

### Predicting the Outcome of Small Battles in StarCraft
- 2014
- <https://www.semanticscholar.org/paper/Predicting-the-Outcome-of-Small-Battles-in-AntonioA./18f148ce9e0bef6ba1dabbb75f0d2a80cdfbabce>
- [[docs/paper3.pdf]]
- 200 коротких реплеев на плоской карте
- Algorithm: LDA, QDA, SVM, KNN, KKNN
	- we compare classical classification algorithms like Linear and Quadratic Discriminant Analysis, Support Vector Machines, and two instancebased classifiers based on the retrieval of the k-Nearest Neighbors (kNN). kNN classifiers can be seen as simple Case-based Reasoning (CBR) systems that only implement the retrieval phase of the CBR cycle.
	- At the micro level players have to combine different types of units, locate them in the map and use their abilities. In this paper we focus on small battles, that is, at the micro level.

### An Analysis of Model-Based Heuristic Search Techniques for StarCraft Combat Scenarios
- 2017
- <https://www.aaai.org/ocs/index.php/AIIDE/AIIDE17/paper/viewPaper/15916>
- [[docs/15916-69776-1-PB.pdf]]
- BWAPI + Sparcraft
- Algorithm: reinforcement learning, model-based heuristic search technique called Portfolio Greedy Search (PGS)
	- A number of heuristic search based approaches for RTS combat have been introduced in recent years, such as AlphaBeta Considering Durations (ABCD), UCT Considering Durations (UCT-CD), and Portfolio Greedy Search (PGS). (Churchill and Buro 2013) demonstrated that PGS outperforms other search-based methods in medium and large-scale combat scenarios, and is currently the top performing heuristic search based method for RTS game combat. As PGS is based on heuristic search, it relies on a forward model of the environment, and its only published results so far have been in simulation, not the StarCraft game engine.

           
### Combining Inﬂuence Maps with Heuristic Search for Executing Sneak-Attacks in RTS Game 
- 2020
- [[docs/cog47356.2020.9231889.pdf]]
- <https://ieeexplore.ieee.org/abstract/document/9231889>
- Algorithm: A* с эвристикой, The influence map projects a radius around the enemies which the Ai wants to avoid to remain stealthy.
	- goal is to use heuristic search to produce a path finding sys tem to effectively execute sneak attacks.
	- specifically focuses on terran drop ships for this.
	- uses a visualizer which draws the game environment as a 2D grid for the influence map where it stores last known locations of units and expected locations.
	- Успешно получилось


### Bayesian Networks for Micromanagement Decision Imitation in the RTS Game Starcraft
- 2013
-  [[docs/parra2013.pdf]]
- <https://link.springer.com/chapter/10.1007/978-3-642-37798-3_38>
- BWAPI
- Algorithm: Bayesian network
	- intends to make a competitive bot using a Bayesian network that fits the actions of the player they are fighting and trained with the micromanagement of that player to keep the bot performance near the player they are fighting.
	- Uses Bayesian network for machine learning which represents itself though DAG (compact acyclic directed graphs). The Bayesian network uses GeNIe (graphical network interface engine) for a graphical editor for node properties and SMILE (structural modeling, interface and learning engine) for conditional dependencies
	- made initial model off of 30 replays and had the player tune the bot based on their priorities
	- made a model for micromanagement by having 2 dragoons vs 3 hydralisks as the basis with the idea that with micromanagement the dragoons can win but without they would loose. Used same player as basis for replays and tuneing
	- ran 50 simulations for the micromanagement to train the bot.
	- Успех 44.5% victories on online matches


### Multi-scale Bayesian modeling for RTS games: an application to StarCraft AI
- 2015
- [[docs/TCIAIG.2015.2487743.pdf]]
- <https://ieeexplore.ieee.org/abstract/document/7293159>
- BWAPI
- 8806 replays using 9/10 with training and 1/10 to test
- Algorithm: Микро на FSM с фоллбеком на Bayesian AI picking best, макро на Bayesian и что-то ещё, не до конца понял
	- intends to use Bayesian model to control three parts of the game Micro-management, tactics, and strategy
	- does not look for a optimal solution just the best it can within the time it has to think
	- breaks the ai down into three smaller AI’s for each part of the game.
	- For micromanagement they used three different tests first a “ﬁnite-state machine” (FSM) and design a basic algorithm that focuses dealing max damage and avoiding it calling it “Heuristic Only AI” (HOAI).  
	- Bayesian AI picking best (BAIPB): this AI follows the above but includes potential for fleeing and more random movement however only picking what it believes is optimal. 
	- Bayesian AI sampling (BAIS): follows the above but does not only do what is optimal and tries less potentially optimal solutions causing a higher randomness from the bot.  
	- they then had them fight each other 200 times BIAS won the most roughly 96% of all fights. Due to less clustering when targeting and chasing targets and being more willing to pull back.
	- tactics model is looking at stealth and choke points when attacking and defending uses normal Bayesian model trained on replays
	- The strategy part attempts to predict the enemy build order and unit production and counter it with its own.
	- Успех 36% пресказания направления атаки противника
	- Успех 58.5% в предсказании результата одиночных битв
	- Успех 63.2% победы в матчах с использованием новой информации
	- Лучшая статья по Bayesian modeling

           
### Combat Models for RTS Games
- 2016
- [[docs/uriarte2017.pdf]]
- <https://ieeexplore.ieee.org/abstract/document/7856990>
- BWAPI
- 600 реплеев
- Algorithm: Monte Carlo Tree Search (MCTS), 3 модели для attrition (TS-Lanchester2, Sustained and Decreasing)
	- MCTS requires a forward model for advancing past the initial game basically a set of orders based on what it understands the current game state is.
	- models combat as an “attrition game” basically only takes hitpoints and offense into consideration no movement.
	- TS-Lanchester2 uses the Lanchester square law and focuses on target selection.
	- Sustained DPF Model (Sustained) models which units can attack each other optimally better but assumes that no units dies and the damage dealt over time does not decrease. Only compares army to army
	- Decreasing DPF Model (Decreasing) Will model unit loss and damage decrease and focuses on one enemy unit at a time rather then the army
	- views map as a graph where number of units is Y and location X or more specifically Perkins’ algorithm.
	- breaks down controlling units into group then squads with each squad its own ai processes
	- sustained was most accurate in predicting battle outcome at 93.6%
	- tested the bots with 100 games
	- Decreasing DPF Model was best at playing the game with a 75% win rate in combat against base AI


### Применение вероятностных и временныз автоматов в программах управления многоагентных систем
- 2020
- [[primenenie-veroyatnostnyh-i-vremennyh-avtomatov-v-programmah-upravleniya-mnogoagentnyh-sistem.pdf]]
- <https://cyberleninka.ru/article/n/primenenie-veroyatnostnyh-i-vremennyh-avtomatov-v-programmah-upravleniya-mnogoagentnyh-sistem>
- Algorithm: Цепи Маркова, вероятностный конечный автомат
	- Обзорная статья без конкретики, но в общем таймеры завязаны на некие условия и меняют конечный автомат
	- Основная фишка что это работает в среде с большой динамикой и множеством неизвестных условий
	- Часть с вероятностями напоминает Utility AI


### Neuroevolution based multi-agent system for micromanagement in real-time strategy games
- 2012
-  <https://www.researchgate.net/publication/266652801_Neuroevolution_based_multi-agent_system_for_micromanagement_in_real-time_strategy_games>
- Не нашёл где скачать

## Match result prediction

### Global State Evaluation in StarCraft
- 2021
- <https://ojs.aaai.org/index.php/AIIDE/article/view/12725>
- [[docs/12725-Article Text-16242-1-2-20201228.pdf]]
- 8000 реплеев не очень профессиональных игроков
- BWAPI
- Algorithm: Logistic regression
	- we areproviding a possible solution to the game result predic-tion problem: given a game state predict which player willgo on to win the game.
	- Our model uses logistic regression (en.wikipedia.org/wiki/Logisticregression/) to give aresponse or probability of the player winning
	- Model weights are learned from replays using logistic regression.
	- UAlbertaBot(code.google.com/p/ualbertabot), which won last year’s AI-IDE StarCraft AI competition, currently uses simulation re-sults to determine if it should engage the opponent in com-bat scenarios or not. If there is evidence that the opponent is not skilled at combat, one might be willing to engage the opponent even whentheir army composition is superior
