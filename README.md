# Densest Subgraph Algorithms: Classification and Implementations

This document provides a comprehensive classification of existing densest subgraph (DSD) algorithms along with their key characteristics and implementation sources.

## I: Original DSD Works

| Graph Type | Algorithm | Key Technique | Complexity | Approx. Ratio | # Iteration | Optimization Time Complexity |
|:-----------|:----------|:--------------|:-----------|:--------------|:-------------|:-----------------------------|
| **Undirected graphs** | FlowExact [1] | Network flow | O (log𝑛 · 𝑡Flow) | O (𝑚) | 1 | N/A |
| | CoreExact [2] | Network flow | O (log𝑛 · 𝑡Flow) | O (𝑚) | 1 | N/A |
| | FWExact [3] | Convex Programming | O (𝑇 · 𝑚 + log𝑇 · 𝑡Flow) | O (𝑚) | 1 | Ω(𝑇) |
| | MWUExact [4] | Convex Programming | O (𝑇 · 𝑚 + log𝑇 · 𝑡Flow) | O (𝑚) | 1 | Ω(𝑇) |
| | FISTAExact [4] | Convex Programming | O (𝑇 · 𝑚 + log𝑇 · 𝑡Flow) | O (𝑚) | 1 | Ω(𝑇) |
| | Greedy [5] | Peeling | O (𝑚 + 𝑛) | O (𝑚) | 2 | N/A |
| | CoreApp [2] | Peeling | O (𝑚 + 𝑛) | O (𝑚) | 2 | N/A |
| | Greedy++ [6] | Peeling | O (𝑇 · 𝑚 log𝑛) | (1 + 𝜖) | Ω(Δ(𝐺)𝜌∗𝐺𝜖2) | Ω(Δ(𝐺)𝜌∗𝐺𝜖2) |
| | FWApp [3] | Convex Programming | O (𝑇 · 𝑚) | (1 + 𝜖) | Ω(𝑚𝑛Δ(𝐺)𝜖2) | Ω(𝑚𝑛Δ(𝐺)𝜖2) |
| | MWUApp [4] | Convex Programming | O (𝑇 · 𝑚) | (1 + 𝜖) | Ω(𝑥) | Ω(𝑥) |
| | FISTAApp [4] | Convex Programming | O (𝑇 · 𝑚) | (1 + 𝜖) | Ω(√𝑚𝑛Δ(𝐺)𝜖2) | Ω(√𝑚𝑛Δ(𝐺)𝜖2) |
| | FlowApp*[7] | Network flow | O (𝑇 · 𝑚 log𝑚) | (1 + 𝜖) | Ω(log𝑚𝜖) | Ω(log𝑚𝜖) |
| **Directed graphs** | DFlowExact [8] | Network flow | O (𝑛² · 𝑡Flow) | O (𝑚) | 1 | N/A |
| | DCExact [9] | Network flow | O (𝑘 · 𝑡Flow) | O (𝑚) | 1 | N/A |
| | DFWExact [10] | Convex Programming | O (𝑇 · 𝑡Fw) | O (𝑚) | 1 | Ω(𝑇) |
| | DGreedy [11] | Peeling | O (𝑛² · (𝑛 + 𝑚)) | O (𝑚) | 2 | N/A |
| | XYCoreApp [9] | Peeling | O (√𝑚 · (𝑛 + 𝑚)) | O (𝑚) | 2 | N/A |
| | WCoreApp [12] | Peeling | O (Δ(𝐺) · 𝑚) | O (𝑚) | 2 | N/A |
| | DFWApp [10] | Convex Programming | O (𝑇 · log1+𝜖 𝑛𝑚) | (1 + 𝜖) | Ω(𝑚·𝜅𝜖2) | Ω(𝑚·𝜅𝜖2) |

**Notes:**
- 𝑛 and 𝑚 denote the numbers of vertices and edges in the graph respectively
- 𝜖 > 0 is a real value
- Δ(𝐺) denotes the highest degree of 𝐺
- 𝜅 is an integer that is proportional to the maximum value of the highest out-degree and in-degree in directed graphs

## Source Code Repository

The implementations for these densest subgraph algorithms can be found at:
🔗 [https://github.com/JayLZhou/DensestSubgraph](https://github.com/JayLZhou/DensestSubgraph)

## references
[1] Andrew V Goldberg. 1984. Finding a maximum density subgraph. University of California Berkeley

[2] Yixiang Fang, Kaiqiang Yu, Reynold Cheng, Laks VS Lakshmanan, and Xuemin Lin. 2019. Efficient algorithms for densest subgraph discovery. PVLDB 12, 11(2019), 1719–1732.

[3] Maximilien Danisch, T-H Hubert Chan, and Mauro Sozio. 2017. Large scale density-friendly graph decomposition via convex programming. In WWW. 233–242.

[4] Elfarouk Harb, Kent Quanrud, and Chandra Chekuri. 2022. Faster and Scalable Algorithms for Densest Subgraph and Decomposition. In NIPS.

[5] Moses Charikar. 2000. Greedy approximation algorithms for finding dense components in a graph. In APPROX. Springer, 84–95.

[6] Digvijay Boob, Yu Gao, Richard Peng, Saurabh Sawlani, Charalampos Tsourakakis, Di Wang, and Junxing Wang. 2020. Flowless: Extracting densest subgraphs without flow computations. In WWW

[7] Yichen Xu, Chenhao Ma, Yixiang Fang, and Zhifeng Bao. 2023. Efficient and Effective Algorithms for Generalized Densest Subgraph Discovery. Proceedings of the ACM on Management of Data 1, 2 (2023), 1–27.

[8] Samir Khuller and Barna Saha. 2009. On finding dense subgraphs. In ICALP. Springer, 597–608.

[9] Chenhao Ma, Yixiang Fang, Reynold Cheng, Laks VS Lakshmanan, Wenjie Zhang, and Xuemin Lin. 2020. Efficient algorithms for densest subgraph discovery on large directed graphs. In SIGMOD. 1051–1066.

[10] Chenhao Ma, Yixiang Fang, Reynold Cheng, Laks VS Lakshmanan, Wenjie Zhang, and Xuemin Lin. 2021. Efficient Directed Densest Subgraph Discovery. ACM SIGMOD Record 50, 1 (2021), 33–40.

[11] Moses Charikar. 2000. Greedy approximation algorithms for finding dense components in a graph. In APPROX. Springer, 84–95.

[12] Wensheng Luo, Zhuo Tang, Yixiang Fang, Chenhao Ma, and Xu Zhou. 2023. Scalable Algorithms for Densest Subgraph Discovery. In ICDE. IEEE.

## II: k-clique DSD Works

[2] Yixiang Fang, Kaiqiang Yu, Reynold Cheng, Laks VS Lakshmanan, and Xuemin Lin. 2019. Efficient algorithms for densest subgraph discovery. PVLDB 12, 11(2019), 1719–1732.

**Source code:** [https://github.com/JayLZhou/DensestSubgraph](https://github.com/JayLZhou/DensestSubgraph)

[13] C Tsourakakis. The k-clique densest subgraph problem, in WWW 2015.

**Source code:** [https://github.com/tsourolampis/triangle-densest-subgraph-problem](https://github.com/tsourolampis/triangle-densest-subgraph-problem)

[14] KClist++: A Simple Algorithm for Finding k-Clique Densest Subgraphs in Large Graphs" (Bintao Sun, Maximilien Danisch, T-H. Hubert Chan, Mauro Sozio; PVLDB 2020

**Source code:** [https://github.com/btsun/kclistpp](https://github.com/btsun/kclistpp)

[15] Y. Zhou, Q. Guo, Y. Fang, and C. Ma, “A counting-based approach for efficient k-clique densest subgraph discovery,” Proceedings of the ACM on Management of Data, vol. 2, no. 3, pp. 1–27, 2024.

**Source code:** [https://github.com/forxenn/KCCA](https://github.com/forxenn/KCCA)

## III: DSD variants

**Density-friendly graph decomposition:** 

[16] N. Tatti and A. Gionis, Density-friendly graph decomposition. In WWW, 2015, pp. 1089–1099. 

[17] M. Danisch, T. H. H. Chan and M. Sozio, Large Scale Density-friendly Graph Decomposition via Convex Programming. In WWW, 2017.

**Source code:** [https://github.com/maxdan94/Density-Friendly](https://github.com/maxdan94/Density-Friendly)


**Locally densest subgraph:** 

[18] C Ma, R Cheng, LVS Lakshmanan, X Han, Finding locally densest subgraphs: a convex programming approach. In VLDB 2022.

**Source code:** [https://github.com/chenhao-ma/LDScvx](https://github.com/chenhao-ma/LDScvx)


**Anchored densest subgraph:** 

[19] Xiaowei Ye, Rong-Hua Li, Lei Liang, Zhizhen Liu, Longlong Lin, and Guoren Wang. 2024. Efficient and Effective Anchored Densest Subgraph Search: A Convex-programming based Approach. In KDD 24.

**Source code:** [https://github.com/LightWant/nrdensity](https://github.com/LightWant/nrdensity)



