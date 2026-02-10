# Undirected Graph Traversal Program Documentation
Data Structures
The program uses an adjacency matrix to represent the undirected graph:

# Adjacency Matrix
 2D array where matrix[i][j] = 1 indicates an edge between vertices i and j, else 0. Symmetric since graph[i][j] == graph[j][i].

Queue Structure - For BFS, includes:

items[MAX] - Integer array storing queue elements.

front - Integer tracking queue front position.

rear - Integer indicating rear position.

# Functions
initQueue - Sets up empty queue with front and rear = -1.

isQueueEmpty - Checks if front == -1 to detect empty queue.

enqueue - Adds vertex to queue rear; sets front=0 if first element.

dequeue - Removes/returns front vertex, updates front/rear pointers.

BFS - Performs Breadth-First Search using queue; visits same-level neighbors before deeper levels, marks visited nodes to prevent revisits.

DFSUtil - Recursive DFS helper: marks vertex visited, prints it, recurses on unvisited neighbors.

DFS - Initializes visited array, calls DFSUtil from starting vertex for depth-first exploration with backtracking.

displayGraph - Formats and prints adjacency matrix as a table showing vertex connections.

Main Method Organization
The main method follows this flow:

Variable Declaration - Sets vertex count, initializes zero-filled adjacency matrix.

Graph Creation - Manually adds edges by setting graph[i][j] and graph[j][i] = 1.

Display Graph Information - Shows vertex count and all edges.

Display Adjacency Matrix - Calls displayGraph for matrix visualization.

BFS Traversal - Runs BFS from vertex 0, prints visit order.

DFS Traversal - Executes DFS from vertex 0, prints traversal sequence.

# Algorithm
BFS Algorithm
Create queue and visited array.

Mark start vertex visited, enqueue it.

While queue not empty:

Dequeue vertex, print it.

Enqueue all unvisited adjacent vertices (marking them visited).

End while.

DFS Algorithm
Initialize visited array.

Call DFSUtil on starting vertex.

In DFSUtil:

Mark current vertex visited, print it.

Recurse DFSUtil on each unvisited adjacent vertex.

Sample Output
text
=== Undirected Graph Traversal ===

Example Graph with 6 vertices (0 to 5)

Edges:
0-1, 0-2, 1-3, 1-4, 2-4, 3-5, 4-5

Adjacency Matrix:
  0 1 2 3 4 5 
0 0 1 1 0 0 0 
1 1 0 0 1 1 0 
2 1 0 0 0 1 0 
3 0 1 0 0 0 1 
4 0 1 1 0 0 1 
5 0 0 0 1 1 0 

Starting from vertex 0:
BFS Traversal: 0 1 2 3 4 5 
DFS Traversal: 0 1 3 5 4 2