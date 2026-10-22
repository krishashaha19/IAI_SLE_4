# SLE-4 — Architecture Decision Record (ADR)

**Student:** Krisha Champalal Shaha  
**PRN:** 25UAM070  
**Division:** A  
**Course:** 02AML204 – Introduction to Artificial Intelligence

## Overview
This repository contains the SLE-4 work for the search-algorithm and Interactive Maze Solver sequence. The main decision in the ADR is to use a **visited set** to avoid expanding the same state repeatedly.

## Architecture decision
Maintain a visited set and check each state before expanding it. This supports BFS and DFS and fits the **Memory / Visited Set** responsibility described in the SLE-3 C4 architecture.

## Evidence from SLE-2
The recorded seven-node graph experiment reported:
- BFS average execution time: **0.006706 ms**
- DFS average execution time: **0.011268 ms**
- Average nodes expanded: **7.00** for both

These measurements describe only this small test graph. They do not prove that BFS is always faster than DFS.

## Related work
- [SLE-2](https://github.com/krishashaha19/IAI_SLE2)
- [SLE-3](https://github.com/krishashaha19/IAI_SLE3)

## Viva explanation
A visited set stores states that have already been explored. It prevents the algorithm from expanding the same state repeatedly and helps avoid cycles. Membership lookup in a set is O(1) on average, although the set uses extra memory.
