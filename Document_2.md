Infix to Postfix Conversion Program Documentation
Data Structures
The program employs a Stack data structure, defined as a structure with two key elements:

stack - A character array that stores stack elements, with a maximum size of 100 elements.

TOP pointer - An integer tracking the index of the topmost element. For an empty stack, it is initialized to -1.

Algorithm
1: Create an empty stack

2: for each character c in the input expression do

3: if c is an operand then

4: Append c directly to the postfix result

5: else if c is an opening parenthesis then

6: Push c onto the stack

7: else if c is a closing parenthesis then

8: repeat

9: Pop from stack and append the popped character to postfix result

10: until an opening parenthesis is found

11: else

12: while stack is not empty AND precedence of c ≤ precedence of top (AND top is not '(') do

13: Pop from stack and append popped operator to postfix result

14: end while

15: Push c onto stack

16: end if

17: end for

18: while stack is not empty do

19: Pop from stack and append popped operator to postfix result

20: end while

21: Return the completed postfix expression

Functions
initStack - Sets up an empty stack by assigning top = -1.

isEmpty - Returns true if top == -1 (stack empty).

isFull - Returns true if top == MAX-1 (stack at capacity).

push - Inserts a character at the top of the stack (if space available), then increments top.

pop - Extracts and returns the top element, decrementing top. Returns null if stack is empty.

peek - Views the top element without removal. Returns null if empty.

isOperand - Determines if a character is alphanumeric (operand).

precedence - Assigns operator priority: exponentiation = 3, *,/ = 2, +,- = 1.

infixToPostfix - Core conversion function that processes each input character: outputs operands immediately, stacks opening parentheses, clears to matching closing parenthesis, handles operator precedence, and empties remaining operators at end.

Main Method Organization
The main function follows these steps:

Variable Declaration - Allocates two character arrays: one for input infix, one for output postfix.

User Input - Prompts for and reads infix expression using fgets.

Conversion - Invokes infixToPostfix to perform the transformation.

Output Display - Shows the final postfix expression on screen.

Sample Output
text
Enter infix expression: A+B*C
Postfix expression: ABC*+