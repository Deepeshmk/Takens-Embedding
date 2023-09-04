# Takens Embedding
This study was done under Dr Amit Apte from IISER Pune as a part of a credited semester project in the Fall Semester of 2021 in IISER Pune.
## Problem Statement:
**Delay Embedding theorems** give a condition under which chaotic dynamical systems can be reconstructed from a sequence of generic observations. The aim of the project was to find these conditions using the time series of the variable $x$ of the [Lorenz Model](https://en.wikipedia.org/wiki/Lorenz_system) and the [Henon Map](https://en.wikipedia.org/wiki/H%C3%A9non_map). Such delay embedding techniques help in a way similar to dimensionality reduction techniques like PCA to improve the characterization, prediction and control of complex dynamical systems. **Takens’ theorem**$^1$ states that for a sufficient number of embedding dimensions, we can reconstruct the attractor by time delay embedding using any time delay value $T$. Such a delay coordinate is defined as $y(k)=[s(k),s (k + T), . . . ,s(k +(d —1)T)]$, where s is the measurement of a coordinate. Thus, finding the appropriate time delay $T$ and appropriate embedding dimension $d$ are the two steps of getting an embedding. 
## Methods: 
### Embedding methods
The embedding methods used were the False Nearest Neighbours(FNN) algorithm for the embedding dimensions and Mutual Information(MI) for optimal time delay values. 
1. **FNN**: Trying to project an attractor onto a very low dimensional space introduces crossings which shouldn’t happen in an embedding. If points in d dimensions are neighbours of one another due to such crossings, we need to eliminate them. In d dimensions, we can define a nearest neighbour $y^{NN}(k)$ for each value of $y(k)$, where $y(k)$ is a point on the reconstructed attractor in $d$ dimensions. For some threshold size $R_T$ (taken to be 20), if $$|s(k+Td)-s^{NN}(k+Td)|/R_d(k)>R_T,$$ then the neighbours are defined as false nearest neighbours. For most of the attractors, we see that the false nearest neighbours are monotonically decreasing with an increase in d. We take the first zero of the FNN function as the embedding dimension.
2. **MI**: For distributions over two random variables X and Y, the mutual information is defined as $$I(X;Y) = \sum_x\sum_y p(x,y) \log(p(x,y)/p(x)p(y)).$$ The average mutual information is calculated for different time delay values, and the first minima of the function are taken as the time step.

## The original and Reconstructed Lorenz Attractors
|![LorenzOriginal](https://github.com/Deepeshmk/Takens-Embedding/assets/139223828/6fb46432-10ef-4ad2-91a4-eb8460efc34d)|
|:-:|
|Original Lorenz Attractor|
|![LorenzReconstructed](https://github.com/Deepeshmk/Takens-Embedding/assets/139223828/0bf6ef52-b24a-4711-a68a-950a3cf1faa9)|
|Reconstructed Lorenz Attractor|

## The original and Reconstructed Henon Attractors
|![HenonOriginal](https://github.com/Deepeshmk/Takens-Embedding/assets/139223828/3360ee4e-ab5e-4322-b2a6-201fd3fcea51)|
|:-:|
|Original Henon Attractor|
|![HenonReconstructed](https://github.com/Deepeshmk/Takens-Embedding/assets/139223828/9aa72431-0b58-478a-926f-e1dd7c643e97)|
|Reconstructed Henon Attractor|


### Metrics or Assessment methods
We used multiple heuristics to assess our reconstruction$^2$ .
1. **Pointwise Distance:** After finding the reconstruction of the attractor, we apply the [Procrustes superimposition](https://en.wikipedia.org/wiki/Procrustes_analysis) on the reconstruction to align it to the original attractor optimally using only rotation, reflection and translation. Once the attractors are aligned, we find the total Euclidean distance between the corresponding points of the attractor and divide it by the total number of points to find a pairwise Euclidean distance. In case this distance is small enough, we accept the reconstruction as working well.
2. We describe the average number 𝜅(k) of the k nearest neighbors of each point on Y’ whose corresponding points match with the k nearest neighbours of the corresponding point on Y. A random sort would give mean of a hypergeometric distribution $k2/N$ and a perfect embedding would give k nearest neighbours. The closer this value is to k, the better is the embedding. We find that the embeddings we find are better than the random sort of points, but not perfect.



## References
1. Sauer, T., Yorke, J. A., & Casdagli, M. (1991). Embedology. Journal of statistical Physics, 65, 579-616.
1. William Gilpin. "Deep reconstruction of strange attractors from time series" 2020. Advances in Neural Information Processing Systems (NeurIPS) 2020 https://arxiv.org/abs/2002.05909
