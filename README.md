# Principles of Artificial Intelligence: Notes for Chapters 1 to 6

These notes summarize Chapters 1 to 6 in sequence. They are written for beginners and include simple examples to make the main ideas easier to understand.

## Chapter 1: Introduction to Artificial Intelligence

Artificial Intelligence, or **AI**, is the study of how to build machines or computer programs that can perform tasks that normally require human intelligence.

Examples of intelligent tasks include:

- understanding language
- solving problems
- planning actions
- recognizing images
- learning from data
- making decisions
- playing games
- controlling robots

### What Is Intelligence?

In AI, intelligence is often connected with the ability to act **rationally**.

A rational system tries to choose the best possible action based on what it knows.

Example:

A navigation app chooses a route to your destination. If one route is shorter but has heavy traffic, the app may choose a longer road that saves time. This is rational behavior because the app is trying to achieve the best outcome.

### Four Ways to Define AI

AI can be described in four main ways:

1. **Thinking humanly**: building systems that think like humans.
2. **Acting humanly**: building systems that behave like humans.
3. **Thinking rationally**: building systems that reason correctly.
4. **Acting rationally**: building systems that choose the best action.

Modern AI often focuses on **acting rationally** because it is practical. We usually care whether the system makes useful decisions.

### Thinking Humanly

Thinking humanly means trying to understand and copy how humans think.

This connects AI with **cognitive science**, psychology, neuroscience, and brain studies.

Example:

If researchers study how humans recognize faces, they may use those ideas to design a computer vision system.

### Acting Humanly: The Turing Test

The **Turing Test** asks whether a computer can communicate so well that a human judge cannot tell whether it is a machine or a person.

The test focuses on behavior. If the computer's answers seem human, it may be considered intelligent under this test.

Example:

A chatbot passes a simple Turing-style test if a user talks with it through text and believes it might be a real person.

### Total Turing Test

The **Total Turing Test** extends the original Turing Test by including perception and physical action.

The system may need:

- natural language processing
- knowledge representation
- automated reasoning
- machine learning
- computer vision
- motor control

Example:

A household robot must understand speech, recognize objects, move around safely, and perform physical tasks.

### Rational Agents

An **agent** is something that observes its environment and acts.

A **rational agent** chooses actions expected to produce the best result.

Example:

A self-driving car is a rational agent if it uses sensors to observe roads, traffic lights, pedestrians, and vehicles, then chooses safe driving actions.

### Foundations of AI

AI is built from many fields:

- **Philosophy**: logic, knowledge, reasoning, mind
- **Mathematics**: algorithms, probability, computation
- **Economics**: utility, decisions, game theory
- **Neuroscience**: brain and nervous system
- **Psychology**: human behavior and learning
- **Linguistics**: language and meaning
- **Computer science**: programming, data structures, computation
- **Control theory and engineering**: systems that act in the physical world

### AI Applications

AI is used in many areas:

- chatbots and virtual assistants
- speech recognition
- machine translation
- recommendation systems
- fraud detection
- medical diagnosis
- self-driving cars
- robotics
- games such as chess and Go

Example:

Netflix recommending movies is an AI application because it learns from viewing patterns and predicts what a user may like.

### AI History and Lessons

AI history includes periods of excitement and disappointment.

Early researchers expected fast progress, but many tasks were harder than expected. Simple demonstrations did not always work in real-world situations.

Important lesson:

Tasks that seem easy for humans, such as walking, seeing, and folding clothes, can be very hard for machines. This idea is related to **Moravec's Paradox**.

## Chapter 2: Intelligent Agents

Chapter 2 explains AI systems as **agents**.

An agent:

- receives information from the environment through **sensors**
- acts on the environment through **actuators**

### Agent, Environment, Sensors, and Actuators

The **environment** is the world the agent operates in.

**Sensors** collect information.

**Actuators** perform actions.

Example:

A robot vacuum:

- Environment: rooms and floors
- Sensors: dirt sensor, wall sensor, location sensor
- Actuators: wheels and suction motor
- Actions: move left, move right, suck dirt, stop

### Agent Function and Agent Program

An **agent function** maps percept histories to actions.

A **percept history** is everything the agent has perceived so far.

An **agent program** is the actual software that implements the agent function.

The basic formula is:

```text
agent = architecture + program
```

Example:

For a robot vacuum:

- architecture: physical vacuum body, sensors, motor
- program: rules or code deciding when to move or clean

### Vacuum-Cleaner World

The vacuum-cleaner world is a simple AI example with two locations, A and B.

Each location can be clean or dirty. The vacuum can move left, move right, suck dirt, or do nothing.

Simple rule:

```text
If current square is dirty, suck.
Else if at A, move right.
Else if at B, move left.
```

This shows how an agent can choose actions based on percepts.

### Rationality

A rational agent chooses the action expected to maximize its **performance measure**.

A performance measure tells us how successful the agent is.

Example:

For a vacuum cleaner, a performance measure may reward:

- clean rooms
- low energy use
- fewer unnecessary movements

An agent can still make mistakes if it has incomplete information or limited time. Rationality means making the best expected decision from available information.

### PEAS

PEAS is a framework for describing an agent's task.

PEAS stands for:

- **Performance measure**
- **Environment**
- **Actuators**
- **Sensors**

Example: automated taxi driver

- Performance measure: safety, speed, legality, passenger comfort, profit
- Environment: roads, traffic, pedestrians, weather
- Actuators: steering, brakes, accelerator, signals, horn
- Sensors: cameras, GPS, speedometer, lidar, radar

### Environment Types

AI environments can be classified in several ways.

**Fully observable vs. partially observable**

- Fully observable: agent can see the complete state.
- Partially observable: agent cannot see everything.

Example:

Chess is fully observable because both players see the whole board. Poker is partially observable because players cannot see each other's cards.

**Deterministic vs. stochastic**

- Deterministic: actions have predictable results.
- Stochastic: randomness is involved.

Example:

Chess is deterministic. Rolling dice in backgammon is stochastic.

**Episodic vs. sequential**

- Episodic: each decision is independent.
- Sequential: current decisions affect future decisions.

Example:

Classifying one email as spam is mostly episodic. Driving a car is sequential because each action affects future road situations.

**Static vs. dynamic**

- Static: environment does not change while the agent thinks.
- Dynamic: environment can change while the agent thinks.

Example:

A crossword puzzle is static. Taxi driving is dynamic.

**Discrete vs. continuous**

- Discrete: separate states and actions.
- Continuous: values can vary smoothly.

Example:

Chess moves are discrete. Steering angle in a car is continuous.

**Single-agent vs. multi-agent**

- Single-agent: only one agent acts.
- Multi-agent: multiple agents interact.

Example:

A calculator solving arithmetic is single-agent. Soccer is multi-agent.

### Agent Types

Common agent architectures include:

- **Simple reflex agent**: acts only on the current percept.
- **Model-based reflex agent**: uses internal state to remember unseen parts of the world.
- **Goal-based agent**: chooses actions that help reach a goal.
- **Utility-based agent**: chooses actions based on how desirable outcomes are.
- **Learning agent**: improves from experience.

Example:

A spam filter is a learning agent if it improves after users mark emails as spam or not spam.

## Chapter 3: Solving Problems by Searching

Search is a method for solving problems by exploring possible states and actions.

In many AI problems, the agent starts in an initial state and tries to reach a goal state.

Example:

In a maze, the initial state is the starting position, the goal state is the exit, and actions are moves such as up, down, left, and right.

### Search Problem Components

A search problem includes:

- **Initial state**: where the problem begins
- **Actions**: possible moves
- **Transition model**: what happens after an action
- **Goal test**: checks whether a state is a goal
- **Path cost**: cost of a sequence of actions

Example: Romania route problem

- Initial state: Arad
- Actions: drive to connected cities
- Transition model: driving from city A to city B puts you in city B
- Goal state: Bucharest
- Path cost: total road distance

### State Space

The **state space** is the set of all states reachable from the initial state.

It can be represented as a graph:

- nodes are states
- edges are actions

Example:

In the Romania map problem, cities are states and roads are edges.

### Vacuum World State Space

In a two-location vacuum world, a state includes:

- where the vacuum is
- whether location A is clean or dirty
- whether location B is clean or dirty

Even this small world has multiple states. Larger problems can have enormous state spaces.

### 8-Puzzle Example

The 8-puzzle has numbered tiles and one blank space. The goal is to slide tiles until the board matches the target arrangement.

States are tile arrangements.

Actions are moving the blank space up, down, left, or right.

Path cost is usually the number of moves.

This example shows how state spaces can grow quickly.

### Tree Search

Tree search explores possible action sequences from the initial state.

Important terms:

- **Node**: a data structure in the search tree
- **State**: a configuration of the world
- **Expand**: generate successors of a node
- **Successor**: a state reached by applying an action
- **Fringe**: nodes generated but not yet expanded

Example:

In a route-finding problem, expanding Arad generates possible next cities such as Sibiu, Timisoara, and Zerind.

### Search Strategy

A **search strategy** decides which node to expand next.

Strategies are evaluated using:

- **Completeness**: will it find a solution if one exists?
- **Optimality**: will it find the best solution?
- **Time complexity**: how many nodes are generated?
- **Space complexity**: how much memory is needed?

Common symbols:

- **b**: branching factor
- **d**: depth of the shallowest solution
- **m**: maximum depth of the state space

## Chapter 4: Search Strategies

Chapter 4 explains specific search strategies.

Search strategies can be divided into:

- **uninformed search**
- **informed search**

### Uninformed Search

Uninformed search uses only the problem definition. It has no extra knowledge about which states are closer to the goal.

### Breadth-First Search

**Breadth-first search**, or BFS, expands the shallowest nodes first.

It uses a FIFO queue:

```text
First in, first out
```

Example:

In a tree, BFS explores all nodes at depth 1 before exploring nodes at depth 2.

Properties:

- complete if branching factor is finite
- optimal if all step costs are equal
- can use a lot of memory

### Uniform-Cost Search

**Uniform-cost search**, or UCS, expands the node with the lowest path cost so far.

It uses a priority queue ordered by cost.

Example:

If one route has 50 km cost and another has 80 km cost, UCS expands the 50 km route first.

Properties:

- complete if step costs are positive
- optimal for path-cost problems
- may be slow if many cheap paths exist

### Depth-First Search

**Depth-first search**, or DFS, expands the deepest node first.

It uses a LIFO stack:

```text
Last in, first out
```

Example:

DFS follows one path in a maze as far as possible before backtracking.

Properties:

- uses less memory than BFS
- not optimal
- not complete in infinite-depth spaces or spaces with loops

### Iterative Deepening Search

**Iterative deepening search**, or IDS, repeatedly runs depth-limited DFS with increasing depth limits.

Example:

Search to depth 1, then depth 2, then depth 3, and so on.

Properties:

- complete for finite branching
- optimal when all step costs are equal
- uses memory like DFS
- finds shallow solutions like BFS

### Informed Search

Informed search uses extra information to guide the search.

This extra information is usually a **heuristic**.

### Heuristic Function

A **heuristic function**, written as `h(n)`, estimates the cost from node `n` to the goal.

Example:

In route finding, straight-line distance to the destination can be a heuristic.

If you are trying to reach Bucharest, a city physically closer to Bucharest may be a better choice.

### Greedy Best-First Search

Greedy best-first search expands the node with the lowest heuristic value.

It uses:

```text
f(n) = h(n)
```

Example:

If city A is 100 km from the goal by straight-line distance and city B is 200 km away, greedy search chooses city A.

Weakness:

It ignores the cost already spent, so it may choose a route that looks close but is actually expensive.

### A* Search

**A* search** combines cost so far and estimated cost to the goal.

It uses:

```text
f(n) = g(n) + h(n)
```

Where:

- `g(n)` is the cost from the start to node `n`
- `h(n)` is the estimated cost from node `n` to the goal
- `f(n)` is the estimated total solution cost through node `n`

Example:

If a route has already cost 120 km and the straight-line distance remaining is 80 km, then:

```text
f(n) = 120 + 80 = 200
```

A* chooses the node with the lowest `f(n)`.

### Admissible Heuristic

A heuristic is **admissible** if it never overestimates the true cost to the goal.

Example:

Straight-line distance is admissible for road travel because the real road distance cannot be shorter than the straight line.

If `h(n)` is admissible, A* can find an optimal solution.

### Designing Heuristics

Good heuristics make search faster.

For the 8-puzzle:

- `h1`: number of misplaced tiles
- `h2`: total Manhattan distance of tiles from their goal positions

Manhattan distance often gives a better estimate because it includes how far each tile is from its correct place.

### Dominance

If one admissible heuristic is always greater than or equal to another, it **dominates** the other.

A dominating heuristic is usually better because it gives a closer estimate without overestimating.

### Weighted A*

Weighted A* gives extra importance to the heuristic:

```text
f(n) = g(n) + W * h(n)
```

where `W > 1`.

This can make search faster, but it may lose optimality.

Example:

A robot may use weighted A* if it needs a good route quickly instead of the perfect shortest route.

### Memory-Bounded Search

A* can use a lot of memory because it stores many nodes.

Memory-bounded methods reduce memory usage.

Examples:

- iterative deepening A*
- recursive best-first search
- simplified memory-bounded A*

## Chapter 5: Informed Search Strategies

Chapter 5 continues informed search and focuses on best-first search, greedy search, A*, IDA*, and SMA*.

### Best-First Search

**Best-first search** selects the most promising node using an evaluation function `f(n)`.

The node with the best value is expanded first.

Example:

If nodes have values 4, 7, and 2, best-first search expands the node with value 2 if lower values are considered better.

### OPEN and CLOSED Lists

Many best-first search algorithms use two lists:

- **OPEN**: generated nodes that have not been expanded
- **CLOSED**: nodes that have already been expanded

OPEN is often a priority queue.

CLOSED helps avoid repeated work.

Example:

In route planning, if the algorithm has already expanded Toronto, it can store Toronto in CLOSED so it does not repeatedly expand the same city.

### Greedy Best-First Search Review

Greedy best-first search uses only the heuristic:

```text
f(n) = h(n)
```

It tries to move toward the goal quickly.

Example:

In the Romania problem, greedy search may choose the city with the smallest straight-line distance to Bucharest.

Advantage:

- often fast

Disadvantages:

- not always complete
- not always optimal
- can be misled by a bad heuristic

### A* Search Review

A* uses:

```text
f(n) = g(n) + h(n)
```

It balances:

- cost already spent
- estimated cost remaining

Example:

Two cities may both look close to the goal, but A* also checks how expensive it was to reach each city.

### IDA*: Iterative Deepening A*

**IDA*** combines ideas from A* and iterative deepening.

Instead of using a depth limit, it uses an `f-cost` limit.

The algorithm repeatedly searches with increasing cost limits.

Example:

First search only nodes with `f <= 366`.

If no solution is found, increase the limit to the next useful value, such as `f <= 393`.

Advantage:

- uses much less memory than A*

Disadvantage:

- may repeat work many times

### SMA*: Simplified Memory-Bounded A*

**SMA*** is a memory-bounded version of A*.

It uses all available memory. When memory is full, it removes the least promising node.

However, it stores enough information in the parent node so it can return to forgotten paths later if needed.

Example:

If a search program can only store 3 paths, SMA* keeps the best-looking paths and forgets the worst one, but remembers its estimated value.

Properties:

- complete if enough memory exists for a solution path
- optimal if enough memory exists for the best solution path
- otherwise finds the best solution it can fit in memory

## Chapter 6: Local Search Algorithms

Chapter 6 introduces local search for optimization problems.

In local search, we usually do not care about the full path to the solution. We care about finding a good final state.

### Optimization Problems

An **optimization problem** asks us to find the best solution according to an objective function.

The goal may be to:

- minimize cost
- maximize score
- minimize conflicts
- maximize profit

Example:

Finding the shortest delivery route is an optimization problem because we want the route with minimum distance.

### Objective Function

An **objective function** measures the quality of a solution.

Example:

For a delivery route, the objective function may be total distance.

For a class schedule, the objective function may count conflicts between courses and rooms.

### Traveling Salesman Problem

The **Traveling Salesman Problem**, or TSP, asks for the shortest tour connecting a set of cities.

State space:

- all possible tours

Objective function:

- length of the tour

Goal:

- minimize total tour length

Example:

A salesperson must visit Toronto, Ottawa, Montreal, and Quebec City, then return home. The best solution is the shortest complete route.

### N-Queens Problem

The **n-queens problem** asks us to place `n` queens on an `n x n` chessboard so that no two queens attack each other.

State space:

- all possible queen configurations

Objective function:

- number of pairwise conflicts

Goal:

- minimize conflicts to 0

Example:

For 8 queens, a solution has 8 queens on the board with no queen sharing a row, column, or diagonal with another queen.

### Hill-Climbing Search

**Hill-climbing search** keeps one current state and repeatedly moves to a better neighboring state.

Basic idea:

```text
Start with a current state.
Look at neighboring states.
Move to the best better neighbor.
Stop when no neighbor is better.
```

Example:

In n-queens, move one queen within its column if doing so reduces the number of conflicts.

If the board has `h = 5` conflicts and a move reduces it to `h = 2`, hill-climbing accepts the move.

### Hill-Climbing Variants

Common variants include:

- choose the best better successor
- choose the first better successor
- randomly choose among better successors

Example:

If three moves reduce conflicts from 5 to 4, 3, and 2, steepest-ascent hill-climbing chooses the move that gives 2.

### Problems With Hill-Climbing

Hill-climbing is not complete and not always optimal.

It can get stuck in:

- **local optimum**: better than nearby states but not the best overall
- **plateau**: many neighboring states have the same value
- **shoulder**: flat area that may lead to better states

Example:

In n-queens, the board may have `h = 1`, but every single queen move may temporarily make the board worse. Simple hill-climbing may stop even though a solution exists.

### Random Restart Hill-Climbing

Random restart hill-climbing runs hill-climbing many times from different random starting states.

Example:

If one starting board gets stuck, restart with a new random n-queens board and try again.

This increases the chance of finding a good solution.

### Local Beam Search

**Local beam search** keeps `k` current states instead of one.

At each step:

1. Generate successors of all `k` states.
2. Choose the `k` best successors.
3. Repeat.

Example:

If `k = 3`, the algorithm keeps the 3 best boards found so far in an n-queens problem.

This is different from running 3 separate hill-climbing searches because the states share information. If one region looks promising, more states can move toward it.

### Simulated Annealing

**Simulated annealing** is a local search method that sometimes accepts worse moves.

This helps escape local optima.

At the beginning, the algorithm accepts bad moves more often. Over time, it becomes less willing to accept bad moves.

This is controlled by a **temperature** value.

Example:

In TSP, a route change might make the tour longer. Simulated annealing may accept this worse route early in the search because it may later lead to a better route.

### Temperature and Annealing Schedule

The **temperature** controls randomness.

- High temperature: more exploration, more bad moves accepted
- Low temperature: less exploration, mostly better moves accepted

The **annealing schedule** tells how temperature decreases over time.

Example:

At high temperature, the algorithm may accept a route that is 10 km worse. At low temperature, it may reject the same route.

### Simulated Annealing Formula

If a move is better, accept it.

If a move is worse, accept it with probability:

```text
exp(Delta / T)
```

Where:

- `Delta` is the change in value
- `T` is the temperature

For a worse move, `Delta` is negative, so the probability becomes smaller.

### MCMC Connection

Simulated annealing is related to a broader family of methods called **Markov Chain Monte Carlo**, or MCMC.

MCMC methods are used to explore complicated state spaces using random movement.

Example:

MCMC can be used in statistics, machine learning, and probabilistic AI to sample from complex distributions.

## Detailed Study Notes and Worked Examples

This section adds more depth to the chapter notes above. Use it after reading the chapter summaries when you want to understand how the ideas connect and how they may appear in examples or exam questions.

## Detailed Chapter 1 Notes: What AI Is Really Trying To Do

AI is not only about making computers "smart" in a general human sense. In most practical systems, AI is about building a program that can choose useful actions in a specific situation.

A useful way to think about AI is:

```text
AI = perception + reasoning/learning + action
```

Not every AI system has all three parts. A recommendation system may not physically act in the world, but it still observes user behavior, learns patterns, and takes an action by recommending an item.

### Human-Like vs. Rational AI

Human-like AI tries to imitate humans.

Rational AI tries to make the best decision.

These are not always the same.

Example:

A human may make a poor driving decision because they are tired or distracted. A rational self-driving car should not copy that mistake. It should choose the safest action.

Another example:

A calculator does not solve arithmetic like a human child, but it gives correct answers quickly. It is not human-like, but it is rational for its task.

### Why the Rational-Agent View Is Useful

The rational-agent view is useful because it focuses on measurable success.

Instead of asking, "Does the machine really think?", we ask:

- What is the agent trying to achieve?
- What information does it have?
- What actions can it take?
- Did it choose a good action?

Example:

For a medical diagnosis system, the important question is not whether it thinks like a doctor. The important question is whether it uses symptoms, test results, and medical knowledge to recommend useful diagnoses or next steps.

### Turing Test Strengths and Weaknesses

The Turing Test is important historically because it gave a behavioral way to discuss machine intelligence.

Strength:

It avoids difficult philosophical questions by focusing on observable behavior.

Weakness:

A system may imitate conversation without truly understanding. It may also be designed to trick the judge rather than solve useful problems.

Example:

A chatbot may give friendly answers and appear intelligent, but it may fail if asked to reason carefully about a new problem.

### The AI Effect

The **AI effect** means that once computers become good at a task, people often stop calling that task AI.

Examples:

- Chess was once considered a strong sign of intelligence. Now chess programs are common.
- Spell check once seemed intelligent. Now it feels ordinary.
- Voice assistants once seemed futuristic. Now they are everyday tools.

This shows that AI is a moving target. As tasks become solved, they often become normal software.

## Detailed Chapter 2 Notes: Understanding Agents

An agent can be very simple or very complex. The agent idea is useful because it gives a common structure for many AI systems.

Basic agent loop:

```text
perceive -> decide -> act -> perceive again
```

Example:

A thermostat senses room temperature, decides whether heating is needed, and turns the heater on or off. This is a simple agent.

A self-driving car senses roads, vehicles, pedestrians, signs, and traffic lights. It then decides how to steer, brake, and accelerate. This is a complex agent.

### Percept vs. State

A **percept** is what the agent senses right now.

A **state** is the actual situation in the environment.

These may be different because the agent may not be able to observe everything.

Example:

In poker, your percept includes your own cards and visible community cards. The full state includes other players' hidden cards, which you cannot see.

This is why many real environments are partially observable.

### Rationality Depends on the Performance Measure

The same behavior can be rational or irrational depending on the performance measure.

Example:

A vacuum cleaner that moves forever between two rooms may be rational if the performance measure only rewards clean rooms and does not penalize movement.

But it is not rational if the performance measure also penalizes wasted energy and time.

This is why designing the performance measure is very important.

### PEAS Worked Example: Spam Filter

For a spam filter:

- Performance measure: reduce spam in inbox, avoid blocking important email
- Environment: user's email account and incoming messages
- Actuators: mark as spam, move to inbox, delete, flag, notify user
- Sensors: email text, sender address, attachments, links, user feedback

False positives and false negatives matter:

- **False positive**: a real email is incorrectly marked as spam.
- **False negative**: a spam email is incorrectly allowed into the inbox.

For many users, false positives are worse because they may miss important messages.

### Agent Types With Examples

Simple reflex agent:

```text
If condition, then action.
```

Example:

If the current square is dirty, the vacuum sucks.

Model-based reflex agent:

It keeps memory of the world.

Example:

A robot vacuum remembers that it already cleaned the kitchen even if it is now in the hallway.

Goal-based agent:

It considers future goals.

Example:

A GPS system chooses roads that help reach a destination.

Utility-based agent:

It compares how good different outcomes are.

Example:

A taxi agent may choose between a fast but expensive route and a slower but safer route.

Learning agent:

It improves with experience.

Example:

A recommendation system learns that a student likes AI videos and recommends more AI content.

## Detailed Chapter 3 Notes: Search Problems

Search is useful when an agent must choose a sequence of actions.

The key idea is to represent the problem clearly. Once the problem is represented as states, actions, and goals, a search algorithm can explore possible solutions.

### Difference Between State Space and Search Tree

The **state space** is the real graph of possible states.

The **search tree** is the tree created while exploring paths.

The same state may appear multiple times in a search tree if it can be reached by different paths.

Example:

In a city map, Arad is one state. But in a search tree, Arad may appear more than once:

- Arad -> Sibiu -> Arad
- Arad -> Zerind -> Arad

This is why repeated-state checking is important.

### Why State Spaces Become Huge

Many AI problems grow very quickly.

Example:

In the 8-puzzle, there are 181,440 reachable states.

In chess, the number of possible games is far larger than the number of atoms in the universe.

This is why search algorithms must be efficient. A method that works for a small puzzle may fail completely on a large problem.

### Worked Example: Maze Search

Suppose an agent is in a maze.

Problem formulation:

- Initial state: starting square
- Actions: move up, down, left, right
- Transition model: moving changes the agent's square unless blocked by a wall
- Goal test: agent is at the exit
- Path cost: number of moves

If all moves cost 1, the optimal solution is the path with the fewest moves.

### Worked Example: Route Search

Suppose you need to travel from City A to City D.

Road distances:

```text
A -> B = 4
A -> C = 2
B -> D = 5
C -> D = 10
```

Possible paths:

```text
A -> B -> D costs 9
A -> C -> D costs 12
```

The optimal path is `A -> B -> D`, even though `A -> C` looked cheaper at first.

This shows why search must consider the total path cost, not just the next step.

### Tree Search vs. Graph Search

Tree search may revisit the same state many times.

Graph search uses an explored set to avoid repeated expansion.

Example:

In a map, graph search avoids endlessly traveling:

```text
Arad -> Sibiu -> Arad -> Sibiu -> ...
```

Graph search is usually more efficient when repeated states are common.

## Detailed Chapter 4 Notes: Comparing Search Strategies

Different search strategies choose different nodes from the fringe. This choice strongly affects performance.

### BFS, DFS, UCS, and IDS Compared

Breadth-first search:

- explores level by level
- good when shallowest solution is desired
- memory expensive

Depth-first search:

- follows one path deeply
- memory efficient
- can get lost in deep or infinite paths

Uniform-cost search:

- expands the cheapest path so far
- good when costs differ
- can explore many low-cost paths before reaching the goal

Iterative deepening search:

- repeats DFS with increasing depth limits
- combines BFS completeness with DFS memory use

### Example: Why BFS Is Not Always Best

Suppose the shallowest solution has 10 steps, but the branching factor is 100.

BFS may need to store an enormous number of nodes before reaching depth 10.

DFS may use much less memory, but it might go down the wrong branch for a long time.

IDS is often a good compromise when all step costs are equal.

### Why Uniform-Cost Search Is Needed

BFS assumes each step has equal cost.

If costs are different, BFS may find a shallow but expensive path.

Example:

Path 1:

```text
Start -> Goal
Cost = 100
```

Path 2:

```text
Start -> A -> Goal
Cost = 2 + 2 = 4
```

BFS may choose Path 1 because it has fewer steps. UCS chooses Path 2 because it has lower total cost.

### Informed Search Intuition

Uninformed search is like exploring without a map.

Informed search is like exploring with a hint about direction.

The heuristic does not need to be perfect. It only needs to be useful.

Example:

Straight-line distance does not equal road distance, but it usually gives a good clue about which city is closer to the destination.

### Greedy Search vs. A*

Greedy search asks:

```text
Which node looks closest to the goal?
```

A* asks:

```text
Which node gives the best estimated total path cost?
```

Example:

Suppose two paths are available:

```text
Node A: g = 100, h = 5, f = 105
Node B: g = 20, h = 40, f = 60
```

Greedy search chooses A because `h = 5` is smaller.

A* chooses B because `f = 60` is smaller than `f = 105`.

This shows why A* is usually more reliable.

### Admissibility and Optimality

An admissible heuristic is optimistic. It never claims the goal is farther away than it really is.

This matters because A* depends on the heuristic not exaggerating the remaining cost.

Example:

If the true remaining road distance is 100 km, an admissible heuristic can say 80 km or 100 km, but not 120 km.

If the heuristic overestimates, A* may skip the truly optimal path.

## Detailed Chapter 5 Notes: Informed Search in Practice

Chapter 5 focuses on how informed search is implemented and improved.

### Evaluation Function in Best-First Search

Best-first search is a general idea. It uses an evaluation function `f(n)` to decide which node looks best.

Different algorithms use different definitions of `f(n)`:

```text
Greedy best-first search: f(n) = h(n)
A* search:              f(n) = g(n) + h(n)
```

This means greedy search and A* are both examples of best-first search.

### Why OPEN and CLOSED Matter

OPEN tells the algorithm what it can still explore.

CLOSED tells the algorithm what it has already explored.

Without CLOSED, the algorithm may repeat work.

Example:

In a road map, you may reach the same city by different routes. CLOSED helps prevent expanding the same city again unless a better path is found.

### IDA* Detailed Explanation

IDA* is useful when A* uses too much memory.

A* stores many nodes in OPEN. IDA* avoids this by doing repeated depth-first searches with an `f-cost` limit.

Example:

Suppose the starting node has:

```text
f = 20
```

IDA* first searches only paths where `f <= 20`.

If no solution is found, it raises the limit to the smallest `f` value that exceeded 20, maybe:

```text
f <= 24
```

Then it searches again.

IDA* uses less memory but may repeat the same early paths many times.

### SMA* Detailed Explanation

SMA* is useful when memory is limited but we still want A*-like behavior.

When memory is full, SMA* removes the worst-looking node. But it records the forgotten node's value in its parent.

This means SMA* can later return to that path if all other paths become worse.

Example:

If a search can only store three nodes, it may forget a path with `f = 50`. If later all remaining paths have `f = 80`, the algorithm knows the forgotten path may be worth restoring.

### When to Use Which Informed Search

Use greedy best-first search when:

- speed is more important than optimality
- a good heuristic is available
- an approximate solution is acceptable

Use A* when:

- optimality matters
- memory is sufficient
- an admissible heuristic is available

Use IDA* when:

- memory is limited
- repeated search is acceptable

Use SMA* when:

- memory is limited
- you want to use available memory as effectively as possible

## Detailed Chapter 6 Notes: Local Search and Optimization

Local search is different from earlier search methods because it usually does not build a path from start to goal.

Instead, it works with complete candidate solutions.

Example:

In the n-queens problem, a candidate solution is a full board with all queens placed, even if some queens are attacking each other.

The algorithm then tries to improve the board.

### Local Search vs. Path Search

Path search:

- starts from an initial state
- finds a sequence of actions
- cares about the path

Local search:

- starts with a complete candidate solution
- makes small changes
- cares mainly about final quality

Example:

For route planning from home to college, the path matters because you need turn-by-turn directions.

For designing a class timetable, the exact path used to create the timetable does not matter. Only the final timetable quality matters.

### Objective Function Examples

An objective function converts solution quality into a number.

For n-queens:

```text
objective = number of attacking queen pairs
```

Lower is better.

For TSP:

```text
objective = total tour distance
```

Lower is better.

For a recommendation system:

```text
objective = predicted user satisfaction
```

Higher is better.

### Hill-Climbing Worked Example

Suppose an n-queens board has 6 conflicts.

The algorithm checks possible moves and finds:

```text
Move A -> 5 conflicts
Move B -> 3 conflicts
Move C -> 7 conflicts
```

Hill-climbing chooses Move B because it gives the best improvement.

Now the current board has 3 conflicts. The process repeats until no better move is found or a solution is reached.

### Local Optimum Example

Suppose a board has 1 conflict, but every single move increases conflicts:

```text
Current state: 1 conflict
Best neighbor: 2 conflicts
```

Hill-climbing stops because no neighbor is better.

But this does not mean the current state is globally best. It may need a temporary bad move before reaching 0 conflicts.

This is why simulated annealing can help.

### Plateau Example

A plateau occurs when many neighboring states have the same value.

Example:

```text
Current state: 4 conflicts
Neighbor A: 4 conflicts
Neighbor B: 4 conflicts
Neighbor C: 4 conflicts
```

The algorithm does not know which direction leads to improvement.

Possible solutions:

- move sideways for a limited number of steps
- choose randomly among equal-value states
- restart from a new random state

### Simulated Annealing Worked Example

Suppose a route has distance 500 km.

A random change creates a route with distance 510 km. This is worse by 10 km.

At high temperature, the algorithm may accept this worse move because it wants to explore.

At low temperature, it will probably reject it.

This behavior allows the search to escape local optima early and become more stable later.

### Why Randomness Helps

Randomness may seem strange, but it is useful when the search space is complicated.

If an algorithm is always greedy, it may get stuck quickly.

Random choices allow it to explore states that do not look immediately good but may lead to better solutions later.

Example:

In TSP, temporarily making the route longer may allow the algorithm to remove a bad crossing later and produce a much shorter tour.

## Quick Comparison of Chapters 1 to 6

| Chapter | Main Idea | Example |
|---|---|---|
| Chapter 1 | What AI is and how it is defined | Turing Test, self-driving car |
| Chapter 2 | AI systems as agents | robot vacuum, automated taxi |
| Chapter 3 | Solving problems by search | maze, Romania route problem |
| Chapter 4 | Search strategies | BFS, DFS, UCS, A* |
| Chapter 5 | Informed search and memory-bounded search | greedy search, IDA*, SMA* |
| Chapter 6 | Local search and optimization | n-queens, traveling salesman |

## Key Terms From Chapters 1 to 6

- **Artificial Intelligence**: building systems that perform tasks requiring intelligence.
- **Agent**: something that perceives and acts.
- **Rational agent**: an agent that chooses actions expected to produce the best outcome.
- **Sensor**: receives information from the environment.
- **Actuator**: performs actions in the environment.
- **Performance measure**: a way to judge success.
- **PEAS**: Performance measure, Environment, Actuators, Sensors.
- **Search problem**: a problem defined by states, actions, goals, and costs.
- **State space**: all possible reachable states.
- **Search tree**: possible action sequences explored by a search algorithm.
- **Fringe**: generated nodes waiting to be expanded.
- **Completeness**: whether a search method finds a solution if one exists.
- **Optimality**: whether a search method finds the best solution.
- **Breadth-first search**: expands shallowest nodes first.
- **Depth-first search**: expands deepest nodes first.
- **Uniform-cost search**: expands lowest-cost paths first.
- **Heuristic**: an estimate used to guide search.
- **Greedy best-first search**: expands the node that appears closest to the goal.
- **A* search**: combines cost so far and estimated cost remaining.
- **Admissible heuristic**: a heuristic that never overestimates true cost.
- **IDA***: memory-efficient A* using increasing cost limits.
- **SMA***: memory-bounded A* that forgets less promising nodes.
- **Local search**: improves candidate solutions without storing full paths.
- **Objective function**: measures solution quality.
- **Hill-climbing**: repeatedly moves to a better neighbor.
- **Local optimum**: a state better than nearby states but not the best overall.
- **Local beam search**: keeps several current states at once.
- **Simulated annealing**: accepts some worse moves to escape local optima.

## Overall Summary

Chapters 1 to 6 build the foundation for understanding AI problem solving.

Chapter 1 introduces AI, rational agents, the Turing Test, AI foundations, and applications. Chapter 2 explains how AI systems can be modeled as agents that perceive and act. Chapter 3 shows how agents solve problems by searching through possible states. Chapter 4 compares major search strategies, including uninformed and informed search. Chapter 5 focuses more deeply on informed and memory-bounded search methods. Chapter 6 introduces local search methods for optimization problems where the goal is to find a good final solution rather than a full path.

The main theme is that AI is about choosing good actions under constraints. Sometimes the agent has complete information and can search systematically. Sometimes it needs heuristics to guide the search. Sometimes the state space is too large, so local search and approximation methods are more practical.
