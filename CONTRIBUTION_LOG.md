# AI Contribution Log — SLE-4

**Student:** Krisha Champalal Shaha  
**PRN:** 25UAM070  
**Division:** A  
**Course:** 02AML204 – Introduction to Artificial Intelligence

| Work item | Contribution / record |
|---|---|
| Review previous SLE work | Connected the SLE-2 BFS/DFS experiment and SLE-3 Interactive Maze Solver to the SLE-4 architecture decision. |
| Identify the problem | Recorded that the same state can be reached more than once, leading to repeated expansion or cycles. |
| Select and document the decision | Documented a visited set and checking a state before expanding it again. |
| Consider alternatives | Compared no visited tracking, list-based tracking, and set-based tracking. |
| Use evidence carefully | Included the reported seven-node test results: BFS average 0.006706 ms, DFS average 0.011268 ms, and 7.00 average nodes expanded for both. These measurements apply only to the small test graph and are not a universal ranking. |
| Explain trade-offs | Recorded reduced duplicate expansion and O(1) average membership lookup, balanced against extra memory and the need for consistent state representation. |
| Prepare for viva | Prepared short explanations of the visited set, alternatives, SLE-2 measurements, SLE-3 C4 responsibilities, and trade-offs. |
| AI assistance disclosure | ChatGPT helped organize and clarify the ADR and viva notes. The student connected the decision to the previous SLE work and is responsible for checking the report against the actual implementation, verifying the measurements, and explaining the decision independently. |

