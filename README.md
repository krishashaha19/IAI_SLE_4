# SLE-4: Architecture Decision Record (ADR)

## Project Title
**Use a Visited Set to Avoid Repeated State Expansion**

## Student Details
- **Name:** Krisha Champalal Shaha
- **PRN:** 25UAM070
- **Division:** A
- **Course:** 02AML204 – Introduction to Artificial Intelligence

## 1. Project Overview
This project explains the use of a visited set in search algorithms such as Breadth-First Search (BFS) and Depth-First Search (DFS). It is related to the Interactive Maze Solver designed in SLE-3.

During graph or maze searching, the same state may be reached multiple times. A visited set helps avoid repeated exploration and unnecessary work.

## 2. Problem Statement
Without visited-state tracking, search algorithms may repeatedly expand the same states and waste computational resources. In cyclic graphs, this can also cause unnecessary looping.

## 3. Architecture Decision
**Decision:** Use a set-based visited structure to track explored states.

Before expanding a state, the search algorithm checks whether it has already been visited. If it has, the state is not expanded again.

## 4. Alternatives Considered

1. **No visited tracking:** Simple to implement, but can cause repeated exploration and cycling.
2. **List-based tracking:** Easy to understand, but membership checks generally take linear time.
3. **Set-based tracking:** Selected because membership checks take O(1) time on average.

## 5. Performance Observations

The SLE-2 experiment compared BFS and DFS on a seven-node graph, starting at A and searching for G.

| Algorithm | Average Execution Time | Average Nodes Expanded |
|---|---:|---:|
| BFS | 0.006706 ms | 7 |
| DFS | 0.011268 ms | 7 |

These results apply only to the tested graph and do not establish that one algorithm is always faster.

## 6. Advantages
- Avoids repeated state expansion.
- Helps prevent unnecessary cycling.
- Provides efficient average membership checks.
- Improves the organization of search logic.
- Supports modular architecture.

## 7. Limitations
- Requires additional memory to store visited states.
- States must have consistent representations.
- Overall performance depends on the search algorithm and problem size.

## 8. SLE Journey
- **SLE-1:** Worked on the search-agent/code task and supporting documentation.
- **SLE-2:** Compared BFS and DFS on a seven-node graph.
- **SLE-3:** Designed an Interactive Maze Solver using four C4 architecture levels.
- **SLE-4:** Documented the decision to use a set for visited-state tracking.

## 9. AI Contribution
ChatGPT was used to clarify the ADR structure, explain alternative approaches, and organize the report and viva notes. The student is responsible for verifying the implementation, measurements, and final documentation.

## 10. References
- [SLE-2 Repository](https://github.com/krishashaha19/IAI_SLE2)
- [SLE-3 Repository](https://github.com/krishashaha19/IAI_SLE3)
