# Principles of Artificial Intelligence: Notes for Chapters 1 to 7

These notes summarize Chapters 1 to 7 in sequence. They are written for beginners and include simple examples to make the main ideas easier to understand.

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

## Chapter 7: Adversarial Search and Games

Chapter 7 explains how AI systems make decisions in competitive situations. In these problems, another player or agent is trying to make choices that may block or reduce our success.

This kind of search is called **adversarial search**.

Examples:

- chess
- checkers
- tic-tac-toe
- Go
- poker
- backgammon
- negotiation or auction systems

### Why Games Are Important in AI

Games are useful in AI because they are formal and measurable.

Most games have:

- clear rules
- legal moves
- winning and losing conditions
- measurable outcomes
- competitive decision-making

Example:

Chess is useful for AI study because the board is visible, the legal moves are clearly defined, and the result is win, lose, or draw.

Games are also good models for real-world competition.

Example:

Business negotiations, military planning, and auctions all involve decision-making where another person or group may respond strategically.

### Types of Game Environments

Games can be classified using ideas from agent environments.

**Perfect information games** are fully observable. Every player can see the complete state.

Examples:

- chess
- checkers
- Go

**Imperfect information games** are partially observable. Players cannot see everything.

Examples:

- poker
- bridge
- Battleships

**Deterministic games** have no randomness.

Example:

Chess is deterministic because the next board position depends only on the move chosen.

**Stochastic games** include randomness.

Example:

Backgammon is stochastic because dice rolls affect possible moves.

### Two-Player Zero-Sum Games

A **two-player zero-sum game** has two players whose interests are directly opposed.

If one player gains, the other player loses.

Example:

In chess, if White wins, Black loses. The utilities can be represented as:

```text
White win:  +1 for White, -1 for Black
Draw:        0 for both
White loss: -1 for White, +1 for Black
```

The sum of the players' utilities is constant.

### Games vs. Single-Agent Search

In single-agent search, the solution is often a fixed path.

Example:

In a maze, the solution may be:

```text
up -> right -> right -> down -> goal
```

In a game, this does not work because the opponent may choose different responses.

Instead, the solution is a **strategy** or **policy**.

A strategy tells the player what move to make in every possible situation.

Example:

In tic-tac-toe, a strategy may say:

- If the center is empty, take the center.
- If the opponent has two in a row, block.
- If you can win immediately, take the winning move.

### Game Tree

A **game tree** shows possible moves and responses.

The root is the current game state.

Branches are legal moves.

Levels alternate between players.

Leaves are terminal states where the game is over.

Example:

In tic-tac-toe:

- MAX may be X.
- MIN may be O.
- Terminal values may be +1 for X win, 0 for draw, and -1 for X loss.

### MAX and MIN

In game search, we often call the players **MAX** and **MIN**.

MAX tries to maximize the utility.

MIN tries to minimize MAX's utility.

Example:

If terminal values are:

```text
3, 12, 8
```

and it is MIN's turn, MIN chooses 3 because that is worst for MAX.

If it is MAX's turn, MAX chooses the largest available value.

### Minimax

**Minimax** is the main algorithm for optimal play in deterministic two-player zero-sum games.

The idea is:

- MAX chooses the move with the highest value.
- MIN chooses the move with the lowest value.
- Values are backed up from terminal states to the root.

Recursive definition:

```text
Minimax(state) =
    Utility(state) if state is terminal
    max Minimax(successors(state)) if player is MAX
    min Minimax(successors(state)) if player is MIN
```

Example:

Suppose MAX has three possible moves. After MIN responds perfectly, the values are:

```text
Move A = 3
Move B = 2
Move C = 2
```

MAX chooses Move A because it guarantees the best worst-case value, 3.

### Why Minimax Is Conservative

Minimax assumes the opponent plays optimally.

This makes it conservative. It protects against the strongest possible opponent.

Example:

If a weaker opponent makes a mistake, MAX may get a better outcome than minimax predicted. But minimax does not depend on the opponent making mistakes.

### More General Games

Not all games are two-player zero-sum games.

Some games have:

- more than two players
- cooperation
- mixed interests
- non-zero-sum utilities

In these games, utilities may be represented as tuples.

Example:

```text
(4, 3, 2)
```

This means:

- player 1 gets utility 4
- player 2 gets utility 3
- player 3 gets utility 2

Each player chooses actions that maximize their own utility.

### Alpha-Beta Pruning

**Alpha-beta pruning** improves minimax by avoiding branches that cannot affect the final decision.

It gives the same answer as minimax, but often searches fewer nodes.

The key idea:

If we already know a branch is worse than a choice we have already found, we do not need to finish searching that branch.

Example:

Suppose MAX already has a move that guarantees value 3.

Now the algorithm examines another move. At a MIN node, it finds one child with value 2.

Since MIN can force value 2, this branch can never be better than MAX's existing value 3. So the remaining children of that MIN node can be skipped.

### Alpha and Beta

**Alpha** is the best value found so far for MAX.

**Beta** is the best value found so far for MIN.

Pruning happens when the current branch can no longer improve the result.

Simple intuition:

- Alpha says, "MAX already has this good an option."
- Beta says, "MIN already has this good an option."
- If a branch cannot beat those bounds, stop searching it.

### Move Ordering

Alpha-beta pruning works best when good moves are considered first.

Example:

In chess, a program may try:

1. captures
2. checks or threats
3. strong positional moves
4. weaker moves

Good move ordering can greatly reduce the number of nodes searched.

With perfect ordering, alpha-beta can reduce search time from about:

```text
O(b^m)
```

to about:

```text
O(b^(m/2))
```

This means the program can effectively search about twice as deep.

### Evaluation Functions

In large games, searching to terminal states is impossible.

Example:

Chess has too many possible games to search all the way to checkmate from the opening position.

So the program cuts off the search at a certain depth and uses an **evaluation function** to estimate the value of the position.

General form:

```text
Eval(s) = w1 f1(s) + w2 f2(s) + ... + wn fn(s)
```

For chess:

- `f1(s)` may count material advantage
- `f2(s)` may measure king safety
- `f3(s)` may measure control of the center
- `f4(s)` may measure pawn structure

Example:

Material values may be:

```text
pawn = 1
knight = 3
bishop = 3
rook = 5
queen = 9
```

If a player is up one queen and down one rook, the material advantage is:

```text
9 - 5 = 4
```

### Horizon Effect

The **horizon effect** happens when a program cuts off search too early and misses something important just beyond the depth limit.

Example:

A chess program may delay losing its queen for two moves. If the search only looks one move ahead, it may think the queen is safe. In reality, the queen is lost just beyond the search horizon.

### Quiescence Search

**Quiescence search** helps reduce the horizon effect.

Instead of stopping at a fixed depth in unstable positions, the program continues searching until the position becomes quieter.

Example:

If a queen is under attack, the program should not stop immediately. It should continue searching captures, checks, or forced moves until the position is more stable.

### Additional Game-Search Techniques

**Transposition table**

Stores game states already evaluated.

Example:

In chess, the same board position may be reached by different move orders. A transposition table avoids evaluating it again.

**Forward pruning**

Ignores moves that seem unlikely to be good.

Example:

A chess program may ignore obviously bad moves to save time.

**Lookup tables**

Store known opening or endgame positions.

Example:

A chess program can use an opening book for the first several moves instead of searching from scratch.

### Games of Chance

Some games include randomness.

Example:

Backgammon includes dice rolls.

To represent this, the game tree includes **chance nodes**.

At a chance node, each outcome has a probability.

Example:

With two dice:

- rolling `(1, 1)` has probability `1/36`
- rolling a total combination like `(1, 2)` or `(2, 1)` has probability `2/36`, which is `1/18`

### Expectiminimax

**Expectiminimax** extends minimax to games with chance.

At MAX nodes, choose the maximum value.

At MIN nodes, choose the minimum value.

At chance nodes, compute the expected value.

Example:

Suppose a chance node has two outcomes:

```text
Outcome A: probability 0.5, value 10
Outcome B: probability 0.5, value 2
```

Expected value:

```text
(0.5 * 10) + (0.5 * 2) = 5 + 1 = 6
```

So the chance node has value 6.

### Monte Carlo Simulation

**Monte Carlo simulation** estimates values by running many random simulations.

Example:

In backgammon, instead of calculating every possible future dice sequence, the program can simulate thousands of random games and estimate which move wins most often.

If Move A wins 620 out of 1000 simulations, its estimated win rate is:

```text
620 / 1000 = 62%
```

### Partially Observable Games

In partially observable games, players cannot see the full state.

Examples:

- poker
- bridge
- Battleships

In poker, you know your own cards but not the opponent's cards.

One method is to randomly generate possible hidden states and analyze them.

This can help, but it does not fully handle bluffing, deception, or information gathering.

### Game-Playing Algorithms Today

Game AI has achieved major successes.

Examples:

- Checkers was solved in 2007.
- IBM Deep Blue defeated Garry Kasparov in chess in 1997.
- Backgammon systems used reinforcement learning to learn strong evaluation functions.
- Modern Go systems made major progress using deep learning and Monte Carlo tree search.

The main lesson is that strong game AI usually combines search, evaluation functions, pruning, learning, and large amounts of computation.

## Quick Comparison of Chapters 1 to 7

| Chapter | Main Idea | Example |
|---|---|---|
| Chapter 1 | What AI is and how it is defined | Turing Test, self-driving car |
| Chapter 2 | AI systems as agents | robot vacuum, automated taxi |
| Chapter 3 | Solving problems by search | maze, Romania route problem |
| Chapter 4 | Search strategies | BFS, DFS, UCS, A* |
| Chapter 5 | Informed search and memory-bounded search | greedy search, IDA*, SMA* |
| Chapter 6 | Local search and optimization | n-queens, traveling salesman |
| Chapter 7 | Adversarial search and games | minimax, alpha-beta pruning, chess |

## Key Terms From Chapters 1 to 7

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
- **Adversarial search**: search where another agent or player is working against the agent.
- **Game tree**: a tree showing possible moves and responses in a game.
- **MAX player**: the player trying to maximize utility.
- **MIN player**: the player trying to minimize MAX's utility.
- **Terminal state**: a final game state where the game is over.
- **Utility**: a numerical value representing the outcome of a state.
- **Zero-sum game**: a game where one player's gain is the other player's loss.
- **Strategy**: a rule that tells a player what move to make in each possible state.
- **Minimax**: a game-search algorithm that chooses the best move assuming the opponent plays optimally.
- **Alpha-beta pruning**: a method for skipping game-tree branches that cannot affect the minimax decision.
- **Evaluation function**: a function that estimates the value of a non-terminal game state.
- **Horizon effect**: an error caused by missing an important event just beyond the search depth limit.
- **Quiescence search**: extending search in unstable positions before applying an evaluation function.
- **Chance node**: a game-tree node representing a random event.
- **Expectiminimax**: minimax extended to handle chance nodes using expected values.
- **Monte Carlo simulation**: estimating values by running many random simulations.
- **Partially observable game**: a game where players cannot see the complete state.

## Overall Summary

Chapters 1 to 7 build the foundation for understanding AI problem solving.

Chapter 1 introduces AI, rational agents, the Turing Test, AI foundations, and applications. Chapter 2 explains how AI systems can be modeled as agents that perceive and act. Chapter 3 shows how agents solve problems by searching through possible states. Chapter 4 compares major search strategies, including uninformed and informed search. Chapter 5 focuses more deeply on informed and memory-bounded search methods. Chapter 6 introduces local search methods for optimization problems where the goal is to find a good final solution rather than a full path. Chapter 7 extends search to competitive settings, where an AI must choose actions while considering an opponent's possible responses.

The main theme is that AI is about choosing good actions under constraints. Sometimes the agent has complete information and can search systematically. Sometimes it needs heuristics to guide the search. Sometimes the state space is too large, so local search and approximation methods are more practical. In games, the agent must also reason about opponents, uncertainty, and limited time.
