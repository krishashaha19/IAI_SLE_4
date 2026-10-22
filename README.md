# SLE-4 — Architecture Decision Record (ADR)

**Student:** Krisha Champalal Shaha  
**PRN:** 25UAM070  
**Division:** A  
**Course:** 02AML204 – Introduction to Artificial Intelligence  
**Date:** 13 October 2026

## Submission files
- [SLE-4 ADR report](SLE4_25UAM070_Krisha_Champalal_Shaha.md) — complete ADR, SLE journey summary, AI contribution note, and viva preparation notes.
- [AI Contribution Log](CONTRIBUTION_LOG.md) — work record and AI-use disclosure.

## Decision in brief
The ADR records the decision to maintain a **visited set** and check whether a state has already been explored before expanding it. This supports BFS and DFS and matches the **Memory / Visited Set** responsibility in the SLE-3 C4 architecture.

## SLE-2 evidence
The reported seven-node graph experiment recorded:
- BFS average execution time: **0.006706 ms**
- DFS average execution time: **0.011268 ms**
- Average nodes expanded: **7.00** for both

These results describe only this small test graph; they do not prove that BFS is always faster than DFS.

## SLE journey
- **SLE-1:** Search-agent/code task and supporting README/contribution documentation.
- **SLE-2:** BFS/DFS profiling and comparison.
- **SLE-3:** Interactive Maze Solver and C4 architecture.
- **SLE-4:** Written justification of the visited-set decision and viva preparation.

## Viva explanation
A visited set stores states that have already been explored. It prevents repeated expansion and helps avoid cycles. Membership lookup in a set is O(1) on average, but the set uses additional memory.

## References
- [SLE-2 repository](https://github.com/krishashaha19/IAI_SLE2)
- [SLE-3 repository](https://github.com/krishashaha19/IAI_SLE3)
