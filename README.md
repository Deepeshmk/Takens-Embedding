# Takens Embedding
This study was done under Dr Amit Apte from IISER Pune as a part of a credited semester project in the Fall Semester of 2021 in IISER Pune.
## Problem Statement:
**Delay Embedding theorems** give a condition under which chaotic dynamical systems can be reconstructed from a sequence of generic observations. The aim of the project was to find these conditions using the time series of the variable $x$ of the [Lorenz Model](https://en.wikipedia.org/wiki/Lorenz_system) and the [Henon Map](https://en.wikipedia.org/wiki/H%C3%A9non_map). Such delay embedding techniques help in a way similar to dimensionality reduction techniques like PCA to improve the characterization, prediction and control of complex dynamical systems.**Takens’ theorem**$^1$ states that for a sufficient number of embedding dimensions, we can reconstruct the attractor by time delay embedding using any time delay value $T$. Such a delay coordinate is defined as $y(k)=[s(k),s (k + T), . . . ,s(k +(d —1)T)]$, where s is the measurement of a coordinate. Thus, finding the appropriate time delay $T$ and appropriate embedding dimension $d$ are the two steps of getting an embedding. 
## Methods: 
### Embedding methods
The embedding methods used were the False Nearest Neighbours(FNN) algorithm for the embedding dimensions and Mutual Information(MI) for optimal time delay values. 
1. **FNN**
2. **MI**





## References
1. Sauer, T., Yorke, J. A., & Casdagli, M. (1991). Embedology. Journal of statistical Physics, 65, 579-616.
1. William Gilpin. "Deep reconstruction of strange attractors from time series" 2020. Advances in Neural Information Processing Systems (NeurIPS) 2020 https://arxiv.org/abs/2002.05909
