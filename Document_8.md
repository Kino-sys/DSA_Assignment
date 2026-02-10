# Sorting Algorithm Program Documentation
This program generates random integers and applies user-selected sorting algorithm from four options while tracking comparisons and swaps.

Data Structures
Stats Structure
Tracks sorting performance metrics:

comparisons - Counts element comparisons during sort.

swaps - Counts element movements/shifts.

Arrays
original - Stores initial random numbers.

arr - Working copy for sorting operations.
Both dynamically allocated based on user-specified size.

# Functions
swap - Exchanges two integer values.

bubbleSort - Repeatedly swaps adjacent out-of-order elements until no swaps needed.

selectionSort - Finds minimum in unsorted portion, swaps to front repeatedly.

insertionSort - Builds sorted prefix by inserting each new element into correct position.

merge - Combines two sorted subarrays into one using temporary storage.

mergeSortHelper - Recursively divides array for merge sort.

mergeSort - Entry point for divide-and-conquer merge sort.

generateRandomArray - Fills array with random values (1-1000).

printArray - Displays array contents.

copyArray - Duplicates source array to destination.

# Main Method Organization
Random Seed - Initializes generator with current time for varied outputs.

Size Input - Validates positive integer for array length.

Memory Allocation - Dynamically creates original/working arrays.

Array Population - Generates random integers (1-1000).

Menu Display - Presents 4 sorting options for user selection.

Array Preparation - Copies original to working array, resets counters.

Pre-sort Display - Shows unsorted array.

Algorithm Dispatch - Switch statement calls selected sort function.

Post-sort Display - Shows sorted result and statistics.

Memory Cleanup - Frees both dynamically allocated arrays.

# Algorithm Descriptions
Bubble Sort Algorithm
Compare adjacent elements from start to end.

Swap if first > second.

Largest element bubbles to end after first pass.

Repeat for shrinking unsorted portion.

Stop early if no swaps in pass.

Selection Sort Algorithm
Partition array into sorted/unsorted regions.

Find minimum in unsorted section.

Swap minimum with unsorted region start.

Expand sorted region, shrink unsorted.

Continue until fully sorted.

Insertion Sort Algorithm
Treat first element as sorted.

Take next unsorted element.

Shift larger sorted elements rightward.

Insert element in correct sorted position.

Repeat for all remaining elements.

Merge Sort Algorithm
Recursively split array into halves.

Continue dividing until single elements.

Merge adjacent sorted pairs bottom-up.

Combine increasingly larger sorted subarrays.

Produce fully sorted array.

Sample Output
text
Enter the number of random integers to generate (N): 10

Choose a sorting algorithm:
1. Bubble Sort
2. Selection Sort
3. Insertion Sort
4. Merge Sort
Enter your choice (1-4): 1

Numbers before sorting:
456 123 789 234 567 890 345 678 901 12

Numbers after sorting:
12 123 234 345 456 567 678 789 890 901

Statistics:
Total Comparisons: 45
Total Swaps: 23