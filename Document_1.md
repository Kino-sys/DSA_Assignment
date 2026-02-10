CODE DOCUMENTATION
Data Structure
The chosen data structure is a Stack.
A stack with a capacity of 6 is initialized, with the top pointer set to -1 using top = -1.
The following functions are implemented:

isEmpty

isFull

push

pop

match_checking

balance_checking

Algorithm
Initialize a Stack

Iterate through the given expression

When encountering any opening bracket, push it onto the stack

When encountering any closing bracket:
a. If the stack is empty → return "UNBALANCED"
b. Pop the top element
c. Verify if the popped element matches the corresponding opening bracket for the closing one; if not → "UNBALANCED"

After processing the entire expression:
a. If stack is empty → "BALANCED"
b. Otherwise → "UNBALANCED"

FUNCTION IMPLEMENTATION
isEmpty:
When the top pointer points to -1 (indicating no valid stack position), the stack is considered empty. This function prevents attempting to pop from an empty stack and generally checks for zero elements.

isFull:
When the stack reaches its maximum capacity with elements, it becomes full and cannot accept more items. This function prevents stack overflow conditions.

push:
Push is a core stack operation. Stacks follow the Last In, First Out (LIFO) principle, so push adds elements to the top. On the first push to an empty stack, top moves to position 0; subsequent pushes increment the top position by one.

pop:
Pop is another essential stack operation. It removes and returns the topmost element. After each pop, the top position decrements by one until the stack becomes empty, at which point popping is not allowed.

matching_checking:
This function is custom-built for this program. It verifies whether the popped element matches the corresponding opening bracket for the detected closing bracket. It takes two parameters (opening and closing brackets) and returns true if any of the three matching conditions are satisfied.

balance_checking:
This main function receives the expression to evaluate. It processes each character, following the algorithm above, and determines if the expression is balanced by applying all necessary checks and utilizing the helper functions.

MAIN FUNCTION:
The main function is straightforward. It tests 3 expressions by passing them to the balance_checking function, which handles all the problem-solving logic.

OUTPUT
text
EXPRESSION: a+(b-c)*(d
UNBALANCED

EXPRESSION: m+[a-b*(c+d*{m)]
UNBALANCED

EXPRESSION: a+(b-c)
BALANCED