# Densest-subgraph-discovery-algorithm-collection
```markdown
# Densest Subgraph Algorithms: Classification and Implementations

This document provides a comprehensive classification of existing densest subgraph (DSD) algorithms along with their key characteristics and implementation sources.

## Table 1: Classification of Existing DSD Works

| Graph Type | Algorithm | Key Technique | Complexity | Approx. Ratio | # Iteration | Optimization Time Complexity | Space Complexity | Early Termination | Graph Reduction | Parallel Friendly |
|:-----------|:----------|:--------------|:-----------|:--------------|:-------------|:-----------------------------|:-----------------|:------------------|:----------------|:------------------|
| **Undirected graphs** | | | | | | | | | | |
| | FlowExact [40] | Network flow | O (log𝑛 · 𝑡Flow) | O (𝑚) | 1 | N/A | | | | |
| | CoreExact [33] | Network flow | O (log𝑛 · 𝑡Flow) | O (𝑚) | 1 | N/A | | | | |
| | FWExact [25] | Convex Programming | O (𝑇 · 𝑚 + log𝑇 · 𝑡Flow) | O (𝑚) | 1 | Ω(𝑇) | | | | |
| | MWUExact [42] | Convex Programming | O (𝑇 · 𝑚 + log𝑇 · 𝑡Flow) | O (𝑚) | 1 | Ω(𝑇) | | | | |
| | FISTAExact [42] | Convex Programming | O (𝑇 · 𝑚 + log𝑇 · 𝑡Flow) | O (𝑚) | 1 | Ω(𝑇) | | | | |
| | Greedy [17] | Peeling | O (𝑚 + 𝑛) | O (𝑚) | 2 | N/A | | | | |
| | CoreApp [33] | Peeling | O (𝑚 + 𝑛) | O (𝑚) | 2 | N/A | | | | |
| | Greedy++ [15] | Peeling | O (𝑇 · 𝑚 log𝑛) | O (𝑚) | (1 + 𝜖) | Ω(Δ(𝐺)𝜌∗𝐺𝜖2) | | | | |
| | FWApp [25] | Convex Programming | O (𝑇 · 𝑚) | O (𝑚) | (1 + 𝜖) | Ω(𝑚𝑛Δ(𝐺)𝜖2) | | | | |
| | MWUApp [42] | Convex Programming | O (𝑇 · 𝑚) | O (𝑚) | (1 + 𝜖) | Ω(𝑥) | | | | |
| | FISTAApp [42] | Convex Programming | O (𝑇 · 𝑚) | O (𝑚) | (1 + 𝜖) | Ω(√𝑚𝑛Δ(𝐺)𝜖2) | | | | |
| | FlowApp*[86] | Network flow | O (𝑇 · 𝑚 log𝑚) | O (𝑚) | (1 + 𝜖) | Ω(log𝑚𝜖) | | | | |
| **Directed graphs** | | | | | | | | | | |
| | DFlowExact [52] | Network flow | O (𝑛² · 𝑡Flow) | O (𝑚) | 1 | N/A | | | | |
| | DCExact [66] | Network flow | O (𝑘 · 𝑡Flow) | O (𝑚) | 1 | N/A | | | | |
| | DFWExact [67] | Convex Programming | O (𝑇 · 𝑡Fw) | O (𝑚) | 1 | Ω(𝑇) | | | | |
| | DGreedy [17] | Peeling | O (𝑛² · (𝑛 + 𝑚)) | O (𝑚) | 2 | N/A | | | | |
| | XYCoreApp [66] | Peeling | O (√𝑚 · (𝑛 + 𝑚)) | O (𝑚) | 2 | N/A | | | | |
| | WCoreApp [60] | Peeling | O (Δ(𝐺) · 𝑚) | O (𝑚) | 2 | N/A | | | | |
| | DFWApp [67] | Convex Programming | O (𝑇 · log1+𝜖 𝑛𝑚) | O (𝑚) | (1 + 𝜖) | Ω(𝑚·𝜅𝜖2) | | | | |

## Source Code Repository

The implementations for these densest subgraph algorithms can be found at:
🔗 [https://github.com/JayLZhou/DensestSubgraph](https://github.com/JayLZhou/DensestSubgraph)

---

**Notes:**
- 𝑛 and 𝑚 denote the numbers of vertices and edges in the graph respectively
- 𝜖 > 0 is a real value
- Δ(𝐺) denotes the highest degree of 𝐺
- 𝜅 is an integer that is proportional to the maximum value of the highest out-degree and in-degree in directed graphs
```
