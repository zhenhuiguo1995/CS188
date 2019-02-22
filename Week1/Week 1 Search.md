#### Week 1: Search

- Reflex agents:

  - chose action based on current percept (and maybe memory), may have memory or a model of the world's current state
  - don't consider future consequences of their actions
  - **not rational** -> rational means reach optimal result

- Planning agents

  - decision based on (hypothesized) consequences of actions

    - must have a model of how to world evolves 

    - must formulate a goal

      

- optimal(for algorithm): achieve goals with min costs

- complete: when there is a solution, this algorithm will find it

- planning and re-planning



A search problem consists of: 

- a state space
- a successor function(with actions and costs)
- a start state and a goal test

A solution:

-  a sequence of actions which transforms the start state to a goal state



Search tree consists of :

- nodes, which stands for paths to states. Nodes represent plans for reaching states, plans has costs



Uninformed search

- dfs
- bfs
- uniform cost search: a search which considers costs
  - slow but stable
  - complete but not optimal



Informed search

- Heuristics(not a search method)
- greedy search
- A*search



Heuristics

- a function that measures how close a state is to a goal
  - should be easy to compute, and give us an estimate of how far away we are with our goal
- designed for a particular search problem

Greedy Search

- strategy: always expand a node that you think is closest to a goal state
- heuristic: estimate of distance to nearest goal for each state

- not always right: local optimal is not always global optimal



A* search

- a combination of uniform cost search(UCS) and greedy search

- A* order by f(n) = h(n) + g(n), where h(n) is the forward cost, g(n) is the backward cost

- should we stop when we enqueue a goal

  - No! Only when we dequeue a goal

- Is A* optimal?

  - not guaranteed to find the optimal. Only if heuristic is chosen wisely

  - Admissible of heuristics:

    - admissible heuristics slow down bad pans but never outweigh true costs
    - a heuristic is admissible(optimistic) if 

    $$
    0 <= h(n) <= h*(n)
    $$

    where $h*(n)$ is the true cost to a nearest goal

  - if heuristics is admissible, then A* is optimal

  - creating admissible heuristics

    - Euclidean distance
    - Manhattan distance

  - A* is essentially a trade-off between quality of estimate and work per node

  - finding admissible heuristic

    - one way think about the relaxed problem, and what heuristic can be applied there -> that heuristic is definitely a suit for the original problem(because it is an underestimate, as more work is actually needed for the "unrelaxed" problem)
    - another way if you have more than one admissible heuristic, then for each node pick the larger of them

  - consistency of A*: if heuristic is consistent, then this algorithm will find the optimal path

    - consistency is a more strict rule compared to admissible



Tree Search- > Graph search

General idea: in tree search, you may fail to detect same routes, which leads to exponential work. Graph search will track the list of nodes which has been expanded and promise not to expand the same state again 

- implementation: tree search + set of expanded states
- still complete
- optimal? Not always, we need consistency of heuristics
  - when we expand, the f cost will never decrease!



Representing a state:

- think about goal test: what information is needed for the goal test
- think about successor function: what information is needed to calculate the successor function















