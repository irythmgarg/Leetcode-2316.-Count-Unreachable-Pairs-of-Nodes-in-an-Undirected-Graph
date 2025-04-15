# Leetcode-2316.-Count-Unreachable-Pairs-of-Nodes-in-an-Undirected-Graph

🌐 Count Unreachable Pairs of Nodes in an Undirected Graph
This repository presents two efficient solutions to Leetcode Problem 2316, where the task is to count the number of unreachable node pairs in an undirected graph. We solve this problem using:

🔍 Depth First Search (DFS)

⚙️ Disjoint Set Union (DSU / Union-Find)

🧠 Problem Overview
You're given n nodes (numbered from 0 to n - 1) and a list of undirected edges. Your goal is to return the total number of unordered pairs of nodes (u, v) such that no path exists between u and v.

A pair is considered unreachable if the nodes belong to different connected components.

✅ Example
Input: n = 5, edges = [[0,1], [2,3], [0,4]]
Output: 2

Explanation:
The graph has two components:
- Component 1: [0, 1, 4]
- Component 2: [2, 3]

Unreachable pairs: (1,2), (1,3)
🚀 Solution Approaches
1. 🔎 Depth First Search (DFS)
This approach uses classic DFS traversal to explore each connected component in the graph.

We construct an adjacency list.

Use DFS to find the size of each component.

Keep track of the number of nodes visited.

Use the formula count += size * (n - visited - size) to count unreachable pairs.

Time Complexity: O(V + E)
Space Complexity: O(V)

2. ⚙️ Disjoint Set Union (Union-Find)
A more efficient and scalable approach, especially for sparse graphs.

Initialize each node as its own parent.

Merge nodes using Union by Rank and Path Compression.

After processing all edges, group nodes by their root representative.

Count the size of each component and calculate unreachable pairs using:

ans += size * (remaining - size) while updating remaining.

Time Complexity: O(α(N)) per operation (where α is inverse Ackermann function, practically constant)
Space Complexity: O(N)

🧮 Formula Used
To count unreachable pairs between components with sizes s1, s2, ..., sk, we use:

Total = s1*(n-s1) + s2*(n-s1-s2) + ... + sk*(n-s1-...-sk)
This avoids overcounting and ensures each pair is considered once.

✨ Conclusion
Both solutions are optimal for their respective use cases. DFS is intuitive and easy to implement, while DSU scales better with dense inputs. Choose based on the size and nature of your graph.


