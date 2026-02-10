Min and Max Heap Construction Program Documentation
Data Structures
The program represents heaps using arrays:

# Array Representation 
Heap elements stored where for index i: left child at 2i+1, right child at 2i+2, parent at (i-1)/2.

Max Heap - Complete binary tree where every parent ≥ its children; largest value at root (index 0).

Min Heap - Complete binary tree where every parent ≤ its children; smallest value at root (index 0).

# Functions
swap - Exchanges values between two integers using temporary storage.

maxHeapify - Restores max-heap property at subtree root i: finds largest among node/children, swaps if needed, recurses.

buildMaxHeap - Converts unsorted array to max heap: calls maxHeapify from last non-leaf node up to root.

minHeapify - Maintains min-heap property at subtree root i: identifies smallest among node/children, swaps, recurses.

buildMinHeap - Transforms unsorted array to min heap: applies minHeapify from last non-leaf upward to root.

displayArray - Prints all array elements sequentially.

# Main Method Organization
The main method demonstrates heap building through these steps:

Data Initialization - Creates unsorted array and calculates its length.

Display Original Array - Shows array before heap operations.

Max Heap Construction - Copies original to new array, builds max heap, displays result.

Min Heap Construction - Copies original again, builds min heap, displays result.

# Algorithm
Build Max Heap Algorithm
Begin at last non-leaf node (n/2 - 1).

For each node from this position to root (index 0):

Apply maxHeapify on current node.

End for.

Max Heapify Algorithm
Set largest = i (current index).

left = 2i + 1; right = 2i + 2.

If left exists and array[left] > array[largest], largest = left.

If right exists and array[right] > array[largest], largest = right.

If largest ≠ i:

Swap array[i] with array[largest].

Recurse maxHeapify(largest).

Build Min Heap Algorithm
Start at last non-leaf node (n/2 - 1).

For each node to root (index 0):

Call minHeapify on current node.

End for.

Min Heapify Algorithm
Set smallest = i.

left = 2i + 1; right = 2i + 2.

If left exists and array[left] < array[smallest], smallest = left.

If right exists and array[right] < array[smallest], smallest = right.

If smallest ≠ i:

Swap array[i] with array[smallest].

Recurse minHeapify(smallest).

# Sample Output
text
=== Min and Max Heap Construction ===

Original Array: 12 11 13 5 6 7 15 9 8 10 

Max Heap: 15 12 13 9 11 7 5 6 8 10 

Min Heap: 5 6 7 8 10 13 15 9 12 11