# Dijkstra's Algorithm - Shortest Path Program Documentation
Data Structures
The program uses these key structures for graph representation and path tracking:

Graph - Represents weighted undirected graph:

vertices - Total number of vertices.

adjMatrix[MAX_VERTICES][MAX_VERTICES] - 2D array storing edge weights (0 = no edge).

PathInfo - Stores shortest path results:

distance[MAX_VERTICES] - Shortest distance from source to each vertex.

parent[MAX_VERTICES] - Parent vertex in shortest path tree.

visited[MAX_VERTICES] - Marks processed vertices.

# Functions
initGraph - Creates empty graph with specified vertices, initializes all matrix entries to 0.

addEdge - Adds bidirectional weighted edge between source and destination vertices.

findMinDistance - Scans unvisited vertices, returns index of minimum distance vertex.

dijkstra - Core algorithm: initializes distances, iteratively selects min-distance vertex, relaxes adjacent edges.

printPath - Recursively prints shortest path from source to target using parent array.

displayResults - Formats and prints distances/paths to all vertices (INF for unreachable).

displayGraph - Prints adjacency matrix in table format showing all connections/weights.

# Main Method Organization
The main function follows this workflow:

Input Validation - Reads/validates vertex count (1 to MAX_VERTICES).

Graph Initialization - Creates empty graph, reads edge count.

Edge Input Loop - Collects source/destination/weight triples with validation (positive weights, valid vertices).

Graph Display - Shows adjacency matrix visualization.

Source Selection - Reads/validates starting vertex.

Algorithm Execution - Runs dijkstra, displays comprehensive results table.

Program Exit - Returns 0 on success.

# Algorithm
Dijkstra's Algorithm
Initialization:

Set all distances to ∞ except source (0).

Mark all vertices unvisited, parents to -1.

Main Loop (V-1 iterations):

Select unvisited vertex u with minimum distance.

If none found, break (graph may be disconnected).

Mark u visited.

Relaxation:

For each adjacent vertex v of u:

If v unvisited and edge exists:

newDist = distance[u] + weight(u,v)

If newDist < distance[v]: update distance[v] and parent[v] = u

Key Properties
Greedy selection of minimum distance vertex ensures optimality.

Works for non-negative weights only.

Time complexity: O(V²) using adjacency matrix.

# Sample Output
text
Enter the number of vertices in the graph: 6
Enter the number of edges: 7

Enter edges (source destination weight):
Edge 1: 0 1 4
Edge 2: 0 2 2
Edge 3: 1 2 1
Edge 4: 1 3 5
Edge 5: 2 3 8
Edge 6: 2 4 10
Edge 7: 3 4 2

========== GRAPH ADJACENCY MATRIX ==========
   0   1   2   3   4 
 0   0   4   2   0   0 
 1   4   0   1   5   0 
 2   2   1   0   8  10 
 3   0   5   8   0   2 
 4   0   0  10   2   0 
============================================

Enter the source vertex: 0

Running Dijkstra's algorithm...

========== SHORTEST PATH RESULTS ==========
Source Vertex: 0

Destination    Distance    Path
-------------------------------------------
0             0         0
1             4         0 -> 1
2             2         0 -> 2
3             6         0 -> 2 -> 1 -> 3
4             8         0 -> 2 -> 4
===========================================