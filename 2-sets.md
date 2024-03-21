# Sets

In Python, a set is a collection of unique elements with no duplicate values. Sets are useful for various operations such as membership testing, removing duplicates from a sequence, and mathematical operations like union, intersection, and difference.

## Basics of Sets

- Sets are defined using curly braces `{}`.
- Elements in a set are unordered, meaning they do not have a defined order.
- Sets do not allow duplicate elements; if you try to add a duplicate element, it will be ignored.

You can create a set like this:

```python
my_set = {1, 2, 3, 4, 5}
```

## Operations on Sets

### Adding and Removing Elements

- **Adding Elements:** You can add elements to a set using the `add()` method.
- **Removing Elements:** Use the `remove()` or `discard()` method to remove elements.

```python
my_set.add(6)     # Adds element 6 to the set
my_set.remove(3)  # Removes element 3 from the set
```

### Set Operations

- **Union (`|`):** Combines elements from two sets, excluding duplicates.
- **Intersection (`&`):** Returns elements common to both sets.
- **Difference (`-`):** Returns elements present in the first set but not in the second.

```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}

union_set = set1 | set2        # {1, 2, 3, 4, 5}
intersection_set = set1 & set2  # {3}
difference_set = set1 - set2    # {1, 2}
```

### Set Membership and Length

- **Membership Test:** You can check if an element is present in a set using the `in` keyword.
- **Length:** Obtain the number of elements in a set using the `len()` function.

```python
if 2 in my_set:
    print("2 is in the set")

set_length = len(my_set)
```

## Immutable Sets

In Python, sets are mutable, but you can create immutable sets using the `frozenset()` function. Immutable sets cannot be changed after creation.

```python
immutable_set = frozenset([1, 2, 3])
```

## Applications of Sets

Sets are particularly useful in scenarios where you need:

- Unique collections of items.
- Fast membership testing.
- Removing duplicates from a collection efficiently.

Sets provide an excellent tool for solving problems related to uniqueness and set operations efficiently.

## Example Problem: Set Intersection

Let's solve a problem using sets. Given two lists of numbers, find the intersection of these lists (i.e., the common elements present in both lists).

```python
def find_intersection(list1, list2):
    set1 = set(list1)
    set2 = set(list2)
    return set1 & set2

list1 = [1, 2, 3, 4, 5]
list2 = [3, 4, 5, 6, 7]

intersection = find_intersection(list1, list2)
print(intersection)  # Outputs: {3, 4, 5}
```

In this example, we convert the lists to sets and then use the intersection operator (`&`) to find the common elements efficiently.

[Back to Welcome Page](0-welcome.md)
