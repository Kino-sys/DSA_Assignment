Doubly Linked List Program Documentation
# Data Structures
The Node structure represents each element in the doubly linked list:

data - Integer value stored in the node.

next - Pointer to the following node (NULL at list end).

prev - Pointer to the preceding node (NULL at list start).

This enables two-way traversal since each node links to both adjacent nodes.

# Functions
createNode - Dynamically allocates memory for a new node, sets its data value, and initializes next/prev pointers to NULL.

insertAfter - Adds a new node immediately after a given node. Updates the specified node's next pointer, new node's prev pointer, and (if exists) the following node's prev pointer.

deleteNode - Removes a target node from the list. Adjusts surrounding nodes' pointers to bypass it, handles head node cases specially, and frees the removed node's memory.

displayList - Traverses from head using next pointers, printing each node's data sequentially.

# Main Method Organization
The main method demonstrates operations in this sequence:

Create nodes: Manually creates four nodes with values 10, 20, 30, 40.

Link Nodes - Manually connects nodes by setting next/prev pointers to form the list.

Display Initial List - Shows the original four-node list.

Insert After Operation - Adds 25 after the 20 node, then redisplays.

Second Insert After - Adds 45 after the 40 node, then redisplays.

Delete Node Operation - Removes the 30 node, then shows final list.

Program Termination - Returns 0 for successful execution.

# Algorithm
Insert After Algorithm
If previous node is NULL, show error and exit.

Allocate new node with given data.

Link new node's next to previous node's original next.

Update previous node's next to new node.

Set new node's prev to previous node.

If new node isn't last, update next node's prev to new node.

Delete Node Algorithm
If list empty or target node NULL, display error and stop.

If deleting head, advance head to next node.

If not last node, set next node's prev to skip deleted node.

If not first node, set previous node's next to skip deleted node.

Free deleted node's memory.

# Sample Output
text
Initial list: 10 20 30 40

Inserting 25 after node with value 20
List: 10 20 25 30 40

Inserting 45 after node with value 40
List: 10 20 25 30 40 45

Deleting node with value 30
List: 10 20 25 40 45