# Stacks

In computer science, a stack is a fundamental data structure that follows the Last In, First Out (LIFO) principle. Imagine a stack of books; you can only take the topmost book or add a new book to the top. This behavior is central to how stacks work in programming.

## Basics of Stacks

A stack has two primary operations:

- **Push:** Adds an item to the top of the stack.
- **Pop:** Removes and returns the top item from the stack.

You can visualize these operations with the following code:

```python
stack = []  # Creating an empty stack

# Pushing items onto the stack
stack.append("item1")
stack.append("item2")
stack.append("item3")

# Popping items from the stack
popped_item = stack.pop()
print(popped_item)  # Outputs: item3

popped_item = stack.pop()
print(popped_item)  # Outputs: item2
```

## Stack Implementation

You can implement a stack using a list in Python. Here's a simple example:

```python
class Stack:
    def __init__(self):
        self.items = []

    def push(self, item):
        self.items.append(item)

    def pop(self):
        if not self.is_empty():
            return self.items.pop()
        else:
            raise IndexError("pop from an empty stack")

    def peek(self):
        if not self.is_empty():
            return self.items[-1]
        else:
            raise IndexError("peek from an empty stack")

    def is_empty(self):
        return len(self.items) == 0

    def size(self):
        return len(self.items)

# Example usage
s = Stack()
s.push(10)
s.push(20)
s.push(30)
print(s.pop())  # Outputs: 30
print(s.peek())  # Outputs: 20
print(s.is_empty())  # Outputs: False
print(s.size())  # Outputs: 1
```

## Applications of Stacks

Stacks are used in various computer science applications, including:

- **Undo mechanisms** in text editors or software.
- **Expression evaluation** such as infix to postfix conversion.
- **Backtracking algorithms** like depth-first search (DFS).
- **Memory management** in function calls (the call stack).

Understanding stacks is crucial for developing efficient algorithms and solving many programming problems.

## Example: Balanced Parentheses

One common problem that can be solved using stacks is checking whether a given string of parentheses is balanced or not. A balanced string of parentheses means that for every opening parenthesis, there is a corresponding closing parenthesis, and they are properly nested.

For example, the strings "()()", "(())", and "(()(()))" are balanced, while ")(", "())(", and "((())" are not balanced.

Let's create a function in Python to solve this problem using a stack:

```python
def is_balanced_parentheses(s):
    stack = []
    opening_brackets = "([{"
    closing_brackets = ")]}"

    for char in s:
        if char in opening_brackets:
            stack.append(char)
        elif char in closing_brackets:
            if not stack:
                return False  # Closing bracket with no matching opening bracket
            top = stack.pop()
            if opening_brackets.index(top) != closing_brackets.index(char):
                return False  # Mismatched opening and closing brackets
    return len(stack) == 0  # Check if stack is empty after processing all characters

# Example usage
print(is_balanced_parentheses("()()"))  # Outputs: True
print(is_balanced_parentheses("(())"))  # Outputs: True
print(is_balanced_parentheses("(()(()))"))  # Outputs: True

print(is_balanced_parentheses(")("))  # Outputs: False
print(is_balanced_parentheses("())("))  # Outputs: False
print(is_balanced_parentheses("((())"))  # Outputs: False
```

In this example, we use a stack to keep track of opening parentheses encountered. When we encounter a closing parenthesis, we check if it matches the top of the stack. If it does, we pop the top element from the stack. If the stack is empty when we encounter a closing parenthesis or if there's a mismatch between opening and closing brackets, the string is not balanced.

You can modify and expand this example to handle other types of brackets or to perform more complex balancing checks.

[Back to Welcome Page](0-welcome.md)
