# Contribution Log — SLE-4

**Student:** Krisha Champalal Shaha  
**PRN:** 25UAM070  
**Division:** A  
**Course:** 02AML204 – Introduction to Artificial Intelligence

| Work item | Contribution / record |
|---|---|
| Review previous SLE work | Connected the SLE-2 BFS/DFS experiment and SLE-3 Interactive Maze Solver to the SLE-4 architecture decision. |
| Identify the problem | Noted that the same state may be reached more than once during search, causing repeated expansion or cycles. |
| Record the decision | Selected a visited set and documented checking whether a state has already been explored before expanding it. |
| Consider alternatives | Compared no visited tracking, list-based tracking, and set-based tracking. |
| Record evidence | Included the reported seven-node test results: BFS average 0.006706 ms, DFS average 0.011268 ms, and 7.00 average nodes expanded for both. These are specific to the small test graph. |
| Document trade-offs | Recorded that a visited set reduces duplicate work and has O(1) average membership lookup, while using additional memory and requiring consistent state representation. |
| Prepare for viva | Prepared a short explanation of the visited set, its benefit, its memory trade-off, and how it fits the SLE-3 Memory / Visited Set component. |
| AI assistance disclosure | ChatGPT was used to help organize and clarify the documentation and viva explanation. The student should verify the final submission and be able to explain the decision and evidence independently. |

