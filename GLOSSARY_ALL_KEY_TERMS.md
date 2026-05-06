# Glossary: definitions, key terms, and concepts

This document explains **vocabulary and ideas** used in the course notes. Terms are grouped **by topic**—not by lecture order. Use your instructor’s exact wording on exams when it differs slightly from what follows.

---

## Symbols and logical notation

**Negation (¬, ~)**  
“Not.” ¬P is true exactly when P is false.

**Conjunction (∧)**  
“And.” P ∧ Q is true only when both P and Q are true.

**Disjunction (∨)**  
“Or” (usually **inclusive**: at least one true makes the whole true).

**Implication (→, ⇒)**  
“If P then Q.” The only *false* row for material implication is P true and Q false; if P is false, P ⇒ Q is considered true regardless of Q—this matches many proof obligations in logic and AI.

**Biconditional (↔, ⇔)**  
“P if and only if Q”; same as (P ⇒ Q) ∧ (Q ⇒ P).

**Universal quantifier (∀)**  
“For all x …” Used to state general laws over a domain of individuals.

**Existential quantifier (∃)**  
“There exists x …” Used to assert that at least one witness satisfies a condition.

**KB**  
**Knowledge base**: the collection of sentences (facts and rules) an agent or prover can use.

**KB ⊢ α (syntactic turnstile)**  
α is **derivable** from KB by applying a fixed set of proof rules in some calculus—the “symbol-pushing” side of logic.

**KB ⊨ α or KB |= α (semantic turnstile)**  
**Entailment**: in every **model** where everything in KB is true, α is also true. Some slides overload **|=** for **satisfiability**; always use the definition given locally.

**α, β**  
 metavariables: placeholders standing for whole formulas, not fixed atoms.

**g(n), h(n), f(n)**  
In path search: **g** is cost from the **start** to node n; **h** is an **estimate** of remaining cost to a goal; **f** often combines them (e.g. f = g + h in A*).

**b, d, m**  
Analysis parameters: **b** ≈ branching factor (max successors), **d** depth of a shallowest goal, **m** maximum path length (possibly infinite).

---

## Artificial intelligence: what it is

**Artificial intelligence (AI)**  
The study and engineering of systems that perform tasks people associate with intelligence: perception, language, reasoning, learning, planning, decision-making, games, robotics, and more. Modern practice mixes **symbolic** methods, **statistical** machine learning, and **hybrid** systems.

**Intelligence (informal)**  
Capacity to learn, adapt, reason, and act effectively across varied situations. In AI the term is **operationalized** by tests, benchmarks, or performance measures rather than a single philosophical definition.

**Rational action**  
Choosing an action that is **sensible** relative to what is known and what counts as success—not the same as “behaving like a human.”

**Thinking humanly**  
Designing or studying systems by modeling **human cognition**—linked to psychology, neuroscience, and cognitive science.

**Acting humanly**  
Designing systems whose **outward behavior** resembles a person; the **Turing Test** family emphasizes this.

**Thinking rationally**  
Using **logic** and correct inference—“the logicist tradition” in AI.

**Acting rationally**  
Choosing actions that maximize **expected** **utility** or performance given beliefs and constraints; a common **textbook** framing for agents.

**Cognitive science**  
Interdisciplinary study of mind and intelligence (psychology, neuroscience, linguistics, philosophy, AI).

**Turing Test**  
A human judge talks (usually in text) with a human and a machine; if the machine cannot be reliably distinguished, some would call it “intelligent” under this **behavioral** criterion. Critics argue behavior can mislead (see Chinese Room).

**Total Turing Test**  
Extends the idea beyond text: adds **vision**, **motor control**, and richer interaction with the physical world—strictly harder.

**Interrogator**  
The judge in a Turing-style setup who questions the participants.

**Chinese Room argument**  
A thought experiment: a person follows rules to manipulate symbols in Chinese without understanding them; outputs look intelligent. The argument challenges the idea that **syntax manipulation alone** equals **understanding**—without settling what “understanding” must involve.

**Moravec’s paradox**  
Tasks that feel “hard” for humans (chess, formal puzzles) can be easier for machines than tasks that feel “easy” (walking, catching a ball, folding laundry). Evolution has made low-level **sensorimotor** skills feel effortless; abstract reasoning feels effortful but is often easier to formalize.

**AI winter**  
Periods when funding and enthusiasm drop because progress, scaling, or reliability did not match earlier promises.

**AI effect**  
The tendency to stop calling a capability “AI” once it works reliably in products—so the public label “AI” keeps shifting toward whatever is still hard.

**Expert systems / knowledge-based systems**  
Systems built around an explicit **knowledge base** (rules, facts) and a **general inference engine**. They highlight **maintainability**: update domain content without rewriting all code.

**Neural networks / connectionism**  
Models built from interconnected units with weights; training adjusts weights from data. Contrasts historically with **symbolic** rule-based AI; modern deep learning dominates many applications.

**Perceptron**  
Early weighted classifier / neuron model—part of the history of learning versus hand-coded rules.

**ELIZA**  
Early **pattern-matching** chatbot: could seem “understanding” by keyword tricks without a real world model—still a lesson in apparent versus genuine competence.

**Blocks World**  
Simplified microworld (blocks, stacks) for planning and vision research; illustrates the gap between **toy** setups and **messy** reality.

**Intractability**  
Many AI problems scale so badly in the worst case that **exact** algorithms are impractical—motivating **heuristics**, **approximation**, and **structure exploitation**.

**Neats vs scruffies**  
Culture clash: **neats** favor clean formal frameworks; **scruffies** favor whatever works in messy practice.

**High-level vs low-level AI**  
Symbolic rules and logic versus signals, features, and learned representations—many systems combine both.

---

## Fields of study that feed AI

**Philosophy**  
Logic, mind, knowledge, language, ethics—framing what “knowing,” “meaning,” and “fairness” might require.

**Mathematics**  
Algorithms, discrete math, logic, probability, optimization, linear algebra—tools for guarantees and for learning.

**Decidability / computability**  
Whether classes of problems admit algorithms that always halt with correct answers—fundamental limits on “perfect reasoning machines.”

**Economics**  
Utility, preferences, decision under uncertainty, **game theory**—useful for rational agents and multi-agent settings.

**Psychology**  
Human perception, learning, and behavior—inspiration and benchmarks for AI systems.

**Linguistics**  
Structure of language—feeds **NLP**.

**Control theory and engineering**  
Stability, feedback, and actuation—essential for robotics and physical agents.

---

## Applications and demos (named systems)

**Natural language processing (NLP)**  
Algorithms for understanding, generating, or translating human language.

**Knowledge representation**  
How facts, types, rules, and structure are **encoded** so programs can store and reason with them (see **Knowledge representation** section below).

**Automated reasoning**  
Algorithms to **derive** conclusions from a KB using logic or rule engines.

**Machine learning**  
Systems that improve performance from **data** or **interaction** by adjusting internal parameters or structure.

**Computer vision**  
Inferring scene structure, objects, motion, or text from **images or video**.

**Motor control**  
Choosing commands for bodies or robots to achieve motion and manipulation goals.

**Speech recognition (ASR)**  
**Speech-to-text**.

**Text-to-speech (TTS)**  
**Text-to-audio** synthesis.

**Dialog systems**  
Conversational agents (customer bots, voice assistants).

**OCR / handwriting recognition**  
Reading printed or handwritten characters from images.

**Face detection vs recognition**  
**Detection**: locate faces; **recognition**: identify **which person** (different tasks).

**Information agents**  
Systems that search, filter, rank, or recommend information (search engines, recommender systems, spam filters).

**Robotics**  
Integrating sensing, planning, learning, and physical action in unstructured environments.

**Logistics, scheduling, planning**  
Choosing **who, what, when, where** under constraints—classic uses of **search** and **constraint** ideas.

**IBM Watson (Jeopardy-era)**  
System combining retrieval, statistical ranking, and NLP for **quiz-style** question answering—example of a **large engineered** pipeline.

**Deep Blue**  
Historic chess system emphasizing **deep search** and **hand-tuned evaluation**—milestone for **game AI**.

---

## Intelligent agents

**Agent**  
Anything that **perceives** through **sensors** and **acts** through **actuators**. The standard loop is: observe → decide → act → repeat.

**Environment**  
Everything outside the agent that matters for the task—other agents, physics, users, institutions.

**Sensor / actuator**  
**Sensor** delivers information; **actuator** changes the world or channels output.

**Perception / percept**  
Raw or processed **observation** at a time step; a **percept history** is the full sequence seen so far.

**Agent function**  
The ideal mapping from **percept histories** to **actions**. It is usually too large to write down explicitly.

**Agent program**  
Concrete code implementing (or approximating) the agent function on a given **architecture**.

**Architecture**  
Hardware and runtime platform on which the **agent program** runs.

**agent = architecture + program**  
Slogan: behavior needs both **physical/computational substrate** and **policy/software**.

**Rational agent**  
An agent that selects actions expected to **maximize** a **performance measure** given its percepts and built-in knowledge. **Rational** means “best expected choice with what you have,” not omniscience.

**Performance measure**  
Objective score of success (safety, profit, cleanliness, accuracy—whatever the designer specifies).

**Utility**  
Numerical **desirability** of an outcome or state—supports **trade-offs** beyond yes/no goals.

**Utility function**  
Maps states or outcomes to utilities so the agent can **compare** alternatives.

**Bounded rationality**  
Real agents have **finite** time, memory, and compute; they **satisfice** or use heuristics instead of perfect optimization.

**PEAS (Performance, Environment, Actuators, Sensors)**  
A checklist to specify a task clearly: what counts as success, what world the agent lives in, what it can affect, what it can sense.

**Vacuum-cleaner world**  
Toy two-square cleaning domain illustrating **percepts**, **actions**, and simple policies.

**NoOp**  
“No operation”—do nothing; sometimes a legal action in toy domains.

**Simple reflex agent**  
Chooses action from the **current** percept only—no internal state for hidden aspects of the world.

**Model-based reflex agent**  
Keeps **internal state** updated from percepts and a **transition model** of how the world changes—handles **partial observability** better than pure reflex.

**Internal state / world model**  
Memory summarizing relevant past; **model** encodes how actions and time change the world.

**Goal-based agent**  
Uses explicit **goals**; often plans with **search** to reach them.

**Utility-based agent**  
Uses a **utility function** to rank outcomes when multiple criteria conflict (speed vs safety).

**Learning agent**  
Improves future behavior from **experience**—components may include model learning, policy learning, or utility estimation.

---

## Classifying environments

**Fully vs partially observable**  
**Fully**: sensors reveal all relevant state (idealized). **Partially**: hidden state exists (other players’ cards, occluded objects).

**Deterministic vs stochastic**  
**Deterministic**: next state fixed by current state and action. **Stochastic**: randomness influences transitions or observations.

**Strategic**  
Deterministic dynamics **but** other agents choose actions too (e.g., chess with perfect information).

**Episodic vs sequential**  
**Episodic**: decisions in one episode do not constrain the next. **Sequential**: early actions change later options.

**Static vs dynamic**  
**Static**: the world does not change while the agent deliberates. **Dynamic**: it can change during “thinking.”

**Semidynamic**  
The **board** may be frozen, but a **clock** or **score** still advances during deliberation.

**Discrete vs continuous**  
**Discrete**: finite or countable states/actions. **Continuous**: real-valued states or controls ( velocities, steering).

**Single-agent vs multi-agent**  
Only one decision maker vs several interacting agents (competition or cooperation).

**Known vs unknown**  
Whether the agent starts knowing **rules and dynamics**; unknown environments require **exploration** or learning.

**False positive / false negative**  
Classification errors: flagging a **bad** instance as positive; or missing a true instance. Central when evaluating filters (e.g., spam).

---

## Classical search (path-finding style)

**Search problem formulation**  
Specify: **initial state**, **actions**, **transition model** (results of actions), **goal test**, **path cost** function. A **solution** is usually a **sequence of actions** reaching a goal.

**State / state space**  
A **state** is a world configuration.**State space** is the set of states **reachable** by legal actions. Often drawn as a **graph**.

**State space graph**  
Vertices are states; edges are actions with costs.

**Search tree**  
Exploration structure: nodes carry path bookkeeping. The **same state** may appear in **multiple** nodes (different paths).

**Search node vs state**  
A **node** includes the state plus metadata (parent, path cost, depth). Multiple nodes can reference one state.

**Fringe / frontier**  
Nodes **generated** but not yet **expanded**.

**Expand a node**  
Generate **successor** nodes by applying every legal action.

**Search strategy**  
Rule that picks **which** fringe node to expand next—defines the algorithm’s behavior.

**Complete (algorithm)**  
If a solution exists under stated assumptions, the algorithm will find **some** solution.

**Optimal (algorithm)**  
Finds a **minimum path cost** solution when that is the defined goal.

**Uninformed (blind) search**  
Uses only the problem definition—no heuristic estimate of “closeness” to goal.

**Informed search**  
Uses extra information—typically a **heuristic** or **evaluation function**—to order exploration.

**Breadth-first search (BFS)**  
Expands **shallow** nodes first (FIFO queue). With **uniform** positive step costs and suitable tie-breaking, finds **shortest** **number-of-step** solutions; memory heavy.

**Uniform-cost search (UCS)**  
Expands lowest **path cost g** so far (priority queue). **Optimal** for nonnegative step costs.

**Depth-first search (DFS)**  
Goes **deep** first (LIFO stack). **Low memory** in many implementations but **incomplete** on infinite depth and not optimal in general.

**Iterative deepening search (IDS)**  
Runs DFS with depth limits 1, 2, 3, … Combines **moderate memory** like DFS with **level-order** flavor for shallow solutions when step costs are uniform.

**FIFO / LIFO**  
First-in-first-out (queue) vs last-in-first-out (stack)—implement BFS vs DFS fringes.

**Priority queue**  
Used when “next node” is the **minimum key** (cost or f-score).

**Explored / CLOSED set**  
Records states already **expanded** to avoid redundant work in **graph search** variants.

**Open list / OPEN**  
Set of **open** nodes awaiting expansion—often implemented as a priority queue in best-first methods.

**Dijkstra’s algorithm**  
Classic **single-source shortest paths** on explicit graphs; building the **full** graph first is often impossible in AI—hence **on-the-fly** tree/graph search.

**Open-loop plan**  
Execute a fixed action sequence **without** replanning from feedback—reasonable only under strong **fully known** **deterministic** assumptions.

**Combinatorial explosion**  
State counts grow as products or exponentials (e.g., sliding puzzles)—motivates heuristics and better formulations.

**Romania map / route finding**  
Pedagogical road-network example for **cost** and **heuristics**.

**8-puzzle / 15-puzzle**  
Sliding-tile puzzles illustrating **state counts** and **heuristic design**.

**Robot motion planning**  
Often **continuous** and high-dimensional; harder than grid toy search.

**Time vs space complexity (search)**  
Asymptotic measures of **generated nodes** and **stored nodes**—used to compare strategies (often using **b**, **d**, **m**).

---

## Heuristics and A*

**Heuristic (informal)**  
Rule of thumb that **guides** decisions; in search, usually a **function** estimating distance or cost to a goal.

**Heuristic function h(n)**  
Estimated **remaining** cost from the node n to a goal. Must match the problem’s cost interpretation.

**Greedy best-first search**  
Expands nodes minimizing **f(n)=h(n)**—aggressively heads toward the goal estimate. Can be **fast** but **incomplete** and **suboptimal** because it ignores cost **already paid**.

**A* search**  
Best-first with **f(n)=g(n)+h(n)**. **g** is actual cost from start; **h** estimates remaining cost; **f** estimates **total** path cost through n.

**Admissible heuristic**  
**Never overestimates** true remaining cost to reach the goal. Under standard conditions, **A\*** with admissible **h** finds **optimal** solutions.

**Dominance (heuristics)**  
If both **h₁** and **h₂** are admissible and **h₂(n) ≥ h₁(n)** everywhere, **h₂** **dominates** **h₁**—usually leads to **fewer** expansions in A*.

**Relaxed problem**  
A **simplified** version of the task (fewer rules). Optimal costs in the relaxation often yield **admissible** heuristics for the real problem.

**Pattern database**  
Precomputed table of exact optimal costs for **subproblems** (e.g., subset of tiles)—builds a **strong admissible** heuristic.

**Combining admissible heuristics**  
**h(n)=max(h₁,…,hₖ)** stays admissible and is **at least** as informed as any single part.

**Weighted A***  
**f = g + W·h** with **W>1**: more **goal-seeking**, often **faster**, may **sacrifice optimality**.

**Optimal efficiency of A\* (informal)**  
Among algorithms with the **same information** (same admissible **h**), A* is **efficient** in the sense that it avoids expanding nodes that **provably** cannot beat the optimal cost—under standard tree-search assumptions.

**Evaluation function f(n)**  
More general than A*: any score ordering nodes in **best-first** search.

**Best-first search**  
General pattern: repeatedly expand the **best** node by **f**, using a priority queue.

**OR graph / multiple paths to one state**  
The same state may be reached by different routes with **different** **g**; algorithms must **track** the best path found so far.

**Memory-bounded search**  
Variants (`IDA*`, `SMA*`, **RBFS**) trade **extra time** (re-expansion) to respect **RAM** limits.

**IDA\* (iterative deepening A\*)**  
Repeated depth-first-like passes with increasing **f-cost** caps instead of pure depth caps. **Low memory**; may **repeat** work.

**SMA\* (simplified memory-bounded A\*)**  
Uses all allowed memory like A*, then **drops** worst-looking nodes but keeps **enough** data to **regrow** forgotten subtrees if they might win.

**RBFS (recursive best-first search)**  
Another **memory-conscious** variant that backs up **f** limits recursively.

**Thrashing**  
Spending time repeatedly **regenerating** parts of the search tree after forgetting them due to memory limits.

---

## Local search and optimization

**Optimization problem**  
Seek a state or parameters that **minimize** or **maximize** an **objective function**; the **path** of moves may not matter.

**Objective function**  
Maps candidate solutions to a **score** (cost, conflicts, distance, profit).

**Local search**  
Improve a **complete candidate** by **local moves** (neighbors); does not necessarily record a path from a distinguished start.

**Successor / neighbor (local search)**  
State reached by a **small change** (swap two cities in a tour; move one queen).

**Hill-climbing (gradient-style discrete)**  
Move to a **better** neighbor while possible—**greedy** and fast but gets stuck on **local optima**, **plateaus**, and **shoulders**.

**Local optimum**  
Better than **all neighboring** states but not globally best.

**Global optimum**  
Best value over the **entire** space.

**Plateau / shoulder / flat local maximum**  
Regions where many neighbors tie or slopes are flat—naive hill-climbing may wander or stop too early.

**Random-restart hill-climbing**  
Run many hill-climbs from random starts to reduce odds of one **bad** basin.

**Local beam search**  
Keep **k** states; each iteration generates children from **all** **k** and keeps the **k best**—beams **concentrate** on promising regions (unlike k independent searches).

**Simulated annealing**  
Randomized local search: **always** accept improving moves; **sometimes** accept **worse** moves with probability depending on **temperature** **T**. Early **high** **T** explores; late **low** **T** exploits.

**Annealing schedule**  
How **temperature** **T** decreases over iterations.

**Δ (delta) in simulated annealing**  
Change in objective when moving to a candidate neighbor.

**MCMC (Markov chain Monte Carlo)**  
Family of stochastic sampling and exploration methods—conceptually related to randomized moves in state spaces.

**Traveling salesman problem (TSP)**  
Find a minimum-cost tour visiting each city once (exact problem statement can vary). Classic **optimization** benchmark.

**N-queens (as optimization)**  
Full board states with **conflict count** as objective; **repair** by local moves.

---

## Games and adversarial search

**Adversarial search**  
Planning when another **player** or adversary reacts to your choices—cannot assume a fixed world response.

**Game tree**  
Nodes are decision points; branches are moves; leaves may be terminal outcomes.

**MAX and MIN**  
Standard **zero-sum** two-player alias: **MAX** tries to maximize a **score**; **MIN** tries to **minimize** MAX’s score.

**Utility**  
Numeric **value** of an outcome for a player at terminal (or estimated) states.

**Zero-sum game**  
One player’s gain equals the other’s loss (up to constants)—perfect opposition in utilities.

**Terminal state**  
Game **over**: win, lose, draw, or scored outcome.

**Strategy / policy**  
Mapping from **situations** to **moves**—not one fixed action sequence, because the opponent varies.

**Perfect vs imperfect information**  
**Perfect**: all relevant state visible (chess). **Imperfect**: hidden information (poker).

**Deterministic vs stochastic games**  
**Stochastic** introduces **chance** (dice, shuffled decks)—needs **expected values**, not only min and max.

**Ply**  
One layer in the **move** structure (half-move in chess terminology in some texts—follow local definitions).

**Minimax**  
Recursive **backup**: MAX nodes take **max** of child values, MIN nodes take **min**, assuming both play **optimally**. **Conservative** against a strong opponent.

**Alpha-beta pruning**  
Skips subtrees that **cannot change** the minimax root decision—**same** optimal move as minimax when implemented correctly.

**α and β**  
Running **bounds** for MAX (**α**) and MIN (**β**) choices along a path—when a branch cannot beat the incumbent, **cut** it.

**Move ordering**  
Trying **likely** strong moves first increases **pruning**; killer moves that often cause cutoffs are good candidates.

**Evaluation function**  
Estimates position value when search **cuts off** before terminals—often a **weighted sum of features** (material, mobility, king safety).

**Horizon effect**  
Forced losses **just beyond** the search depth look “avoided” because the evaluator cannot see them—**quiescence** mitigates.

**Quiescence search**  
Extend search along **tactical** lines (captures, checks) before static evaluation in chess-like games.

**Transposition table**  
Cache of **positions** and scores—same board state via different move orders (**transpositions**).

**Forward pruning**  
**Ignore** some moves to save time—**risks** blunders if a pruned line was critical.

**Opening book / endgame databases**  
Stored **knowledge** replacing search in early or late phases.

**Chance node**  
Random outcome splits the tree (dice, cards)—value is an **expectation** over children.

**Expectiminimax**  
Extends minimax: **max** at MAX, **min** at MIN, **expectation** at chance nodes.

**Monte Carlo rollouts**  
Simulate many random or semi-random playouts to estimate win rate or value from a position.

**Monte Carlo tree search (MCTS)**  
Builds a **search tree** biased by **statistics** from rollouts—famously effective in Go-class games with huge branching.

**Partially observable games**  
Players reason about **beliefs** over hidden state; tricks include sampling possible worlds (**averaging over clairvoyance**)—approximate for poker-like deception.

**Multi-player / non-zero-sum**  
Utilities become **vectors**; each player maximizes **their own** component at their turns.

**Killer move heuristic**  
Promote moves that frequently **prune** siblings in other branches.

**Singular extension**  
Deepen selectively when one move appears **unusually** strong—addresses **horizon** in chess engines.

**Reinforcement learning in games**  
Learning **value functions** or **policies** from self-play—used historically in backgammon and widely today.

---

## Constraint satisfaction problems (CSP)

**Constraint satisfaction problem (CSP)**  
Choose a **value for each variable** from its **domain** so that **all constraints** are satisfied. Many tasks (coloring, Sudoku, scheduling) share this template.

**Variable**  
One decision to assign (region color, digit in cell, queen column…).

**Domain**  
Set of values a variable may take (may **shrink** during inference).

**Assignment**  
Maps variables to values—**partial** or **complete**.

**Constraint**  
A relation forbidding some value **combinations**—**unary**, **binary**, or **global** (e.g., **alldifferent**).

**Consistent partial assignment**  
No constraint **involving only assigned** variables is violated.

**Complete assignment**  
Every variable has a value.

**Solution**  
**Complete** and **consistent** assignment.

**Constraint graph**  
Variables as **nodes**; **binary** constraints as **edges**—helps intuition and algorithms.

**Factored representation**  
State described by **many variables** instead of one opaque “state ID”—enables **local** reasoning.

**Alldifferent (alldiff)**  
A **global** constraint: selected variables must take **pairwise distinct** values (Sudoku rows/columns/blocks).

**Map coloring**  
Variables are regions; adjacent regions must **differ** in color—classic CSP.

**Cryptarithmetic**  
Letter-as-digit puzzles; constraints include **column addition**, **carries**, **leading nonzero**, **alldiff** on letters.

**Sudoku as CSP**  
Cells are variables; domains are digits; **alldiff** on rows, columns, blocks.

**N-queens formulations**  
Can use **N²** 0/1 variables or **N** variables (queen per row with column domains)—**formulation** drastically affects search size.

**Incremental / backtracking search**  
Assign variables one by one (depth-first). On failure, **undo** (**backtrack**) and try other values.

**Commutativity of assignments**  
A full solution is **unordered** in meaning—**variable order** is an algorithmic device.

**SELECT-UNASSIGNED-VARIABLE / ORDER-DOMAIN-VALUES**  
Pseudocode “hooks” where **heuristics** plug in for **which variable** next and **which value** to try first.

**MRV (minimum remaining values)**  
Choose the unassigned variable with the **smallest** current **legal** domain—**fail-first** principle surfaces dead ends early.

**Degree heuristic / most constraining variable**  
Among **MRV ties**, pick the variable touching the **most** still **unassigned** neighbors—often breaks ties on **high-degree** hubs.

**LCV (least constraining value)**  
Given a chosen variable, prefer a value that removes the **fewest** options from **neighbors**—keeps future flexibility (**costly** to compute exactly).

**Forward checking**  
After assigning **X=v**, remove from each **unassigned neighbor** any value **inconsistent** with **v**; **empty** domain ⇒ immediate **backtrack**.

**Constraint propagation**  
Repeatedly **delete impossible domain values** using constraints—stronger than “check only when assigning.”

**Arc consistency (AC)**  
For a directed arc **(Xᵢ,Xⱼ)**, every value left in **Dᵢ** must have at least one **supporting** value in **Dⱼ** satisfying their constraint.

**REVISE**  
Operation that removes **unsupported** values from the tail domain of an arc.

**AC-3**  
Maintains a **queue** of arcs; **REVISE**; whenever a domain **shrinks**, enqueue arcs into that variable—until **quiescence** or **failure** (empty domain).

**MAC (maintaining arc consistency)**  
After each **assignment** in backtracking, re-establish **arc consistency**—**stronger** pruning than bare forward checking alone.

**k-consistency**  
Generalizations beyond pairwise consistency—**stronger** **local** tests; full **global** solving still needs structure or search in general.

**Arc consistency does not guarantee a solution**  
Domains can be nonempty and pairwise consistent yet **no global** assignment exists (classic **parity / cycle** intuitions).

**MIN-CONFLICTS**  
**Local** CSP repair: start from a **complete** assignment; repeatedly pick a conflicted variable and set it to a value minimizing **constraint violations**—often scales to huge N-queens-style problems but is **not** always complete.

**Soft constraints / constraint optimization**  
Allow **weighted** violations or minimize **penalty**—many real engineering problems.

**Vision as CSP (line labeling)**  
Assign discrete **labels** to **edges/junctions** under **legal catalogs**—compatibility constraints resemble Sudoku-like pruning.

**SAT (Boolean satisfiability)**  
Is there a truth assignment making a Boolean formula **true**? Central **NP-complete** problem.

**NP-complete (informal)**  
No known **polynomial-time** algorithm for **all** worst-case instances; practical solvers still handle many **structured** cases.

**Cook–Levin**  
Foundational result identifying SAT as **NP-complete**.

**Reduction**  
Many CSP decision problems **map** to SAT or coloring—complexity links.

**CSPLib**  
Public library of **benchmark** constraint models.

---

## Logic: language, meaning, proof

**Logic**  
Formal **syntax** (legal formulas), **semantics** (when formulas are true), and **proof rules** (safe transformations).

**Knowledge-based agent**  
Splits **knowledge base** (content) from **inference engine** (machinery)—supports **TELL** and **ASK** style interaction.

**Knowledge base (KB)**  
Set of sentences treated as **available premises**.

**Syntax**  
Which symbol strings or trees are **well-formed formulas**.

**Semantics**  
Which **interpretations** or **models** make a sentence **true**.

**Model**  
Assignment or structure giving **truth values** or **meanings** to symbols so sentences can be evaluated.

**Atomic sentence / proposition symbol**  
Indivisible **P**, **Q** in propositional logic.

**Logical connectives**  
¬ ∧ ∨ ⇒ ⇔—combine simpler sentences.

**Truth table**  
Exhaustive table of truth for a formula over finitely many atoms—**exponential** in the number of atoms.

**Logical equivalence**  
Two formulas true in **exactly** the same models.

**De Morgan laws**  
¬(P∧Q) ≡ ¬P∨¬Q; ¬(P∨Q) ≡ ¬P∧¬Q—move negation **inward**.

**Contrapositive**  
P ⇒ Q is equivalent to ¬Q ⇒ ¬P.

**Valid (tautology)**  
True in **every** model.

**Satisfiable**  
True in **at least one** model.

**Unsatisfiable (contradiction)**  
True in **no** model—**P ∧ ¬P** is the classic pattern.

**Entailment (KB ⊨ α)**  
Whenever KB is true, α must be true too—**semantic consequence**.

**Model checking (brute force)**  
Enumerate all assignments to **n** atoms (2ⁿ rows)—conceptually simple, rarely scalable.

**Inference procedure**  
Algorithm producing formulas claimed to **follow** from KB.

**Soundness**  
If the procedure outputs α, then **KB ⊨ α**—**no false positives**.

**Completeness**  
If **KB ⊨ α**, the procedure can **eventually** derive α—**no false negatives** in principle (for the logic + calculus considered).

**Modus ponens**  
From α and α⇒β, infer β—the **workhorse** of rule-based forward steps.

**∧-introduction / ∧-elimination**  
Build or split conjunctions.

**∨-introduction**  
From α infer α∨β—disjunction introduction is **easy** directionally.

**Double negation elimination**  
From ¬¬α infer α (in classical logic).

**Unit resolution**  
From α∨β and ¬β infer α.

**Resolution**  
Rule on **clauses**: resolve two clauses containing complementary **literals** to produce a new clause—basis of many **automated provers**.

**Clause / literal**  
**Literal**: atom or negated atom.**Clause**: disjunction of literals.

**CNF (conjunctive normal form)**  
**AND** of **OR-clauses**—standard target form for resolution.

**Refutation (proof by contradiction)**  
To prove **KB ⊨ α**, show **KB ∧ ¬α** is **unsatisfiable**—derive **empty clause** via resolution in the propositional setting.

**Empty clause**  
Signified **contradiction**—end of a successful refutation proof.

**Definite clause**  
Disjunction with **exactly one positive literal**—reads as an **if-then** **rule** with a single **head** atom.

**Rule body / head**  
**Body**: conjunction of conditions; **head**: concluded atom (definite clause view).

**Horn clause**  
At most **one** positive literal per clause—**Horn** theories support efficient **chaining** and align with **Prolog** fragments.

**Forward chaining**  
Start from known facts; whenever a rule’s **body** is satisfied, **assert** its **head**; repeat—**data-driven**.

**Backward chaining**  
Start from **goal**; find rules whose **head** matches; prove **bodies** recursively—**goal-driven**.

**AND–OR view**  
AND nodes gather **all** premises of a rule; OR nodes combine **alternative** rules for the same conclusion.

**co-NP-complete (mention)**  
Complexity class touchstone for some logical tasks—signals **hard** worst cases.

---

## First-order (predicate) logic

**Propositional logic**  
Combines **whole statements** with connectives—compact but **cannot** economically express “**all** x satisfy …” without **grounding** many instances.

**Predicate / first-order logic (FOL)**  
Adds **predicates**, **constants**, **functions**, **quantifiers**—talks about **objects** and **relations**.

**Predicate symbol**  
Denotes a property or relation: Man(x), Likes(x,y).

**Constant symbols**  
Named individuals.

**Function symbols**  
Build **terms** (e.g., motherOf(x)) that denote objects.

**Variables**  
Placeholders ranging over a domain—bound by quantifiers.

**Terms**  
Constants, variables, or **nested function applications**—denote objects.

**Atomic formula**  
Predicate applied to a tuple of terms—basic truth bearer in FOL.

**Quantifiers ∀ and ∃**  
Express **generality** and **existence**—core for scientific laws and database-like facts.

**Interpretation**  
Specifies a domain, meanings for constants/functions/predicates—defines truth of formulas.

**Valuation (propositional layer)**  
Maps each atom to **true/false** (0/1).

**Expressive power**  
FOL captures **patterns over infinitely many** instances with finite axioms—what propositional logic needs enormous groundings to mimic.

**Logical calculus (formulas)**  
Calculus = system of **formula** manipulations—not differential calculus.

**Unification**  
Find substitutions making two expressions **identical**—needed for rule matching with variables (Prolog’s core).

**Skolemization**  
Standard step removing **∃** in **clause** conversion by introducing **Skolem constants/functions**—preserves **satisfiability** properties used in refutation proofs; details belong to proof theory courses.

**Resolution principle (FOL)**  
Lifts clause resolution with **unification**—uniform machine reasoning after normalization.

**Natural deduction**  
Proof style with **many** introduction/elimination rules—pleasant for **human** proofs, not the same minimal engine as raw resolution.

---

## Rules, engines, and knowledge representation

**Knowledge representation (KR)**  
Choosing **languages** and **structures** to encode the world: what is easy to **say**, **infer**, **maintain**, and **retrieve**.

**Declarative knowledge**  
**What** is true: facts, rules, constraints—often **separated** from control.

**Procedural knowledge**  
**How** to do things: programs, scripts, prioritized procedures.

**Heuristic knowledge**  
Imperfect but useful **shortcuts** for search and decision.

**Data vs knowledge**  
Raw measurements vs **interpreted** facts tied to **meaning** and **action** (e.g., a number vs a diagnosis).

**Belief vs hypothesis**  
**Belief**: treated as working truth; **hypothesis**: explicitly tentative pending evidence.

**Epistemology**  
Philosophical study of the nature and limits of **knowledge**—occasionally referenced when KR discusses “belief” formally.

**Metaknowledge**  
Facts **about** the KB: provenance, confidence, timestamps, cost of using a rule.

**Inference / reasoning engine**  
Software implementing **chaining**, **resolution**, or other calculi over a KB.

**Control strategy**  
Policy for **which** rule or subgoal to try next—even “declarative” KBs acquire **procedural** flavor via **order** and **tie-breaking**.

**General problem solver (historical idea)**  
Hope for **one** broad reasoning core for all domains—contrasts with **domain knowledge** emphasis in successful **expert** systems.

**Expert-system shell**  
Reusable **interpreter** with empty KB **slots**; domain experts fill rules—**maintenance** win.

**Representational / inferential / acquisitional adequacy and efficiency**  
Classic design checks: can we **say** it, **derive** it, do it **fast**, and **edit** the knowledge easily.

**Inheritance (is-a / instance)**  
Organize defaults along **taxonomies**—specific objects **inherit** typical properties unless **overridden**.

**Unary vs binary relations**  
Properties of one object vs **relations** between two (parent, loves, greater-than).

**Symbolic structures**  
Encodings designed for **algorithmic** manipulation—not just unstructured text blobs.

**Relational tables**  
Store **tuples**; **some** answers require **computation** (max, sum), not only **stored** facts.

**Rule sides (if / then)**  
**Antecedent** conditions vs **consequent** effects—forward matching uses **if**; backward uses **then** to spawn **subgoals**.

**TELL / ASK**  
**TELL** adds facts (often triggers forward propagation); **ASK** poses queries (natural fit for backward).

**Antecedent / consequent**  
**If** part and **then** part of an implication or rule.

**Renaming (variables)**  
Consistently swapping variable labels does not change **logical content**—matching algorithms treat renamings as same **schema**.

**Renaming vs real difference**  
`Likes(x,x)` and `Likes(x,y)` are **structurally** different; do not confuse with harmless renames.

**OPS5 / CLIPS (examples)**  
Classic **forward-chaining production-rule** systems with **working memory**.

**MYCIN / EMYCIN (examples)**  
Historic **consultation** lineages often taught as **backward** / goal-driven **rule** consultation with **explanation** traces.

**Conflict set**  
Several rules **match** simultaneously—engine must **choose**.

**Conflict resolution**  
Policies: **salience**, **recency**, **specificity**, **refraction** (avoid repeating fires), etc.

**Salience**  
Numeric **priority** among rules.

**Working memory**  
Current **fact set** in production systems—**LHS** of rules match against it.

**RETE algorithm**  
Compiles rule networks for **incremental** updates when facts change—reduces cost for large rule bases.

**Matching**  
Deciding **which** rule instances apply to current patterns—may include **variables** and **partial** states.

**Indexing**  
Data structures (keys, discrimination trees) mapping **features** of states to **candidate** rules—avoids scanning all rules every cycle.

**Approximate / fuzzy matching**  
Treat **similar** sensory patterns as “close enough” when exact match is unrealistic.

**Forward vs backward reasoning (control view)**  
**Data-driven** propagation vs **goal-driven** justification—same KB may support both **modes**.

**Bidirectional / hybrid reasoning**  
Mix **evidence arrival** with **goal focus** (e.g., diagnosis with streaming labs).

**Logic programming**  
Programming paradigm where **clauses** resemble logic; **Prolog** is the iconic language.

**Horn clauses (Prolog connection)**  
Prolog programs are **Horn**-shaped in standard presentations—enables **goal-directed** execution.

**Prolog-style control**  
Typical engine: **backward** chaining over Horn rules, tries clauses **top-to-bottom**, **depth-first**, with **backtracking** on failure—**order** matters for behavior and even termination.

**SLD-resolution**  
Formal operational semantics underpinning standard Prolog execution.

**Negation as failure (NAF)**  
Prolog’s `not` is often **non-monotonic** operational negation—**not** the same as classical ¬ in all programs.

**Goal / subgoal**  
Query execution reduces **goals** to **subgoals** until **facts** unify.

**Witness (existential)**  
Concrete term **t** demonstrating ∃x P(x); engines may return **one** or **enumerate many** answers.

**Declarative vs procedural controversy**  
**Semantics** may fix **truth**, but **implementation** still chooses **order**—different orders can yield **different first answers** with the same logical reading.

**Resolution + clause form (KR angle)**  
Converting KB and negated query to **clauses** and **resolving** supports uniform **automated** proving—can obscure human-readable structure unless layered with explanation tools.

**Refutation proving**  
Assume **negation** of goal with KB; derive **contradiction** to establish entailment.

---

## Pedagogical examples (toys)

**Vacuum world / Romania map / 8-puzzle**  
Standard teaching domains for search—small enough to **trace** by hand.

**Fritz / Tweety (frogs and canaries)**  
Toy rules chaining **behaviors** → **species** → **color**—illustrates forward and backward passes on the **same** rules.

**Marcus / Caesar (logic story)**  
Classic sentences for practicing **FOL** encodings (citizenship, loyalty, assassination).

**Australia map (CSP)**  
Map coloring with a **high-degree** interior region—illustrates **MRV** and **degree** heuristics.

---

## Closing note

If a term appears on a slide but not here, treat that as a **gap to close**: add a short definition in your own notes using the same style—**one paragraph** that says what it is, **why** it matters, and **one** example.

*End of glossary.*
