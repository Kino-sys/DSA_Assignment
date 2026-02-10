Linked List Reverse Traversal Program Documentation
# Data Structures
The program defines a Node structure for each linked list element:

data - Integer variable holding the node's value.

next - Pointer to the subsequent node. Set to NULL for the final node.

This structure allows nodes to connect in a chain, forming a singly linked list where each node points to the next one.

# Functions
createNode - Allocates memory for a new node, stores the given data, and initializes next to NULL.

insertEnd - Adds a new node at the list's tail. Makes it the head if list is empty; otherwise, traverses to end and links it.

displayForward - Prints list elements from head to tail by iterating through nodes.

reverseTraversal - Core recursive function for reverse printing: calls itself until list end, then prints on return path.

displayReverse - Wrapper that invokes reverseTraversal with "Reverse:" prefix formatting.

freeList - Traverses list and deallocates all nodes to avoid memory leaks.

Main Method Organization
The main function executes these steps:

Variable Declaration - Declares head pointer and input variables.

User Input - Requests number of elements to create.

List Creation - Loops to collect element values and appends each via insertEnd.

Display Output - Shows forward traversal, then reverse traversal.

Memory Cleanup - Invokes freeList to release all allocated memory.

Program Termination - Returns 0 for successful completion.

Algorithm
Reverse traversal uses recursion to print linked list elements backward:

Base case: If current node is NULL, return.

Recursive step: Call reverseTraversal on next node until end.

Print step: Output current node's data after recursive calls return.

Recursion reverses order naturally: calls proceed forward, prints occur during unwind.

For list 10 → 20 → 30 → 40:

Calls recurse: 10→20→30→40→NULL

Returns printing: 40, 30, 20, 10

Time complexity: O(n) (visits each node once).
Space complexity: O(n) (recursion stack holds n frames max).

# Sample Output
Enter the number of elements: 5
Enter 5 elements:
10
20
30
40
50
Forward: 10 20 30 40 50
Reverse: 50 40 30 20 10