# SLE-4: Final Viva & Architecture Decision Record (ADR)

**Course:** 02AML204 – Introduction to Artificial Intelligence  
**PRN:** 25UAM070  
**Name:** Krisha Champalal Shaha  
**Division:** A  
**Date:** 13 October 2026

## Part A — Architecture Decision Record (ADR)

**Title:** Use a Visited Set to Avoid Repeated State Expansion  
**Status:** Accepted  
**Date:** 13 October 2026  
**PRN & Name:** 25UAM070 — Krisha Champalal Shaha

### 1. Context
My SLE work explores search algorithms and pathfinding. In SLE-2, I compared BFS and DFS on a seven-node graph, starting at A and searching for G. In SLE-3, I described an Interactive Maze Solver that searches a grid containing start, goal, and obstacle positions. During graph or maze search, the same state may be reached more than once. Without tracking visited states, the program can repeat work and may loop on cyclic graphs. I needed a simple way to remember which states had already been explored.

### 2. Decision
I chose to maintain a visited set in the search logic and check a state before expanding it again. This supports BFS and DFS and fits the **Memory / Visited Set** responsibility in the SLE-3 C4 design.

### 3. Alternatives Considered
- **No visited tracking:** simpler initially, but repeated states can be expanded and cycles can cause unnecessary work.
- **List of visited states:** easy to understand, but membership checking generally requires a linear scan.
- **Set-based visited structure — chosen:** makes duplicate-state tracking clear and provides O(1) average membership lookup.

### 4. Rationale / Justification
The SLE-2 experiment recorded an average time of approximately **0.006706 ms for BFS** and **0.011268 ms for DFS**; both expanded an average of **7 nodes** on the small test graph. These results are a baseline for that particular graph, not proof that one algorithm is always faster. A visited set helps both searches avoid expanding a state repeatedly, reducing duplicated work. In SLE-3, Memory / Visited Set is separated from the Search Engine, making each responsibility easier to understand and maintain. The search strategy can vary—for example, FIFO queue behavior for BFS, LIFO stack behavior for DFS, or priority-based exploration for A*—while state tracking remains a separate concern. Set membership is O(1) on average, which is preferable to repeatedly scanning a list as the number of states grows. For a larger maze, a visited set can reduce repeated exploration, although total runtime and memory use still depend on the algorithm and maze.

### 5. Consequences

**Positive**
- Reduces duplicate state expansion and helps prevent repeated cycling through states.
- Provides O(1) average membership checks.
- Matches the separate Memory / Visited Set responsibility in the C4 architecture.

**Negative / Trade-offs**
- Uses additional memory to store visited states.
- State representation must be consistent so the same position is recognized as the same state.

### 6. References
- [SLE-2 repository](https://github.com/krishashaha19/IAI_SLE2)
- [SLE-3 repository](https://github.com/krishashaha19/IAI_SLE3)

## Part B — Short Summary of My SLE Journey
In SLE-1, I worked on the search-agent/code task and its supporting documentation. In SLE-2, I compared BFS and DFS on the same seven-node graph and recorded execution-time and node-expansion measurements. In SLE-3, I represented an Interactive Maze Solver using the four C4 levels, from system context to code-level functions. The design separates input, search, heuristic, memory/visited tracking, and output responsibilities. In SLE-4, I documented the decision to use a set for visited-state tracking because it reduces repeated work and fits the architecture.

## Part C — AI Contribution Note
**AI tools used:** ChatGPT.  
**What AI helped with:** Organizing the ADR, explaining alternatives and trade-offs, and preparing a clear viva explanation.  
**My contribution and responsibility:** I connected the decision to my previous SLE work and its reported measurements and architecture. I am responsible for checking the final report against my actual implementation, verifying the measurements, and explaining the decision independently during viva.

## Part D — Viva Preparation Notes
- **Why use a visited set?** It stops the search from expanding the same state repeatedly and helps avoid cycles.
- **Why a set instead of a list?** A set has O(1) average membership lookup; a list generally needs a linear scan.
- **What did SLE-2 show?** On my seven-node graph, BFS averaged about 0.006706 ms and DFS about 0.011268 ms; both expanded 7 nodes on average. This small test is not a universal ranking.
- **What does the SLE-3 C4 design show?** It separates Input, Search Engine, Heuristic, Memory / Visited Set, and Output responsibilities.
- **What is the trade-off?** The visited set uses extra memory but avoids unnecessary repeated expansion.
