# program-113
from __future__ import annotations

def rec_insertion_sort(collection: list, n: int):
    # Checks if the entire collection has been sorted
    if len(collection) <= 1 or n <= 1:
        return
    insert_next(collection, n - 1)
    rec_insertion_sort(collection, n - 1)

def insert_next(collection: list, index: int):
    # Checks order between adjacent elements
    if index >= len(collection) or collection[index - 1] <= collection[index]:
        return
    # Swaps adjacent elements since they are not in ascending order
    collection[index - 1], collection[index] = collection[index], collection[index - 1]
    insert_next(collection, index + 1)

# Test examples
lists_to_sort = [
    [4, 3, 5, 1, 2],
    [5, 9, 10, 3, -4, 5, 178, 92, 46, -18, 0, 7],
    [1.1, 1, 0, -1, -1.1, 0.1]
]

for nums in lists_to_sort:
    print("\nOriginal list:")
    print(nums)
    rec_insertion_sort(nums, len(nums))
    print("After applying Recursive Insertion Sort:")
    print(nums)
output
Original list:
[4, 3, 5, 1, 2]
After applying Recursive Insertion Sort:
[1, 2, 3, 4, 5]

Original list:
[5, 9, 10, 3, -4, 5, 178, 92, 46, -18, 0, 7]
After applying Recursive Insertion Sort:
[-18, -4, 0, 3, 5, 5, 7, 9, 10, 46, 92, 178]

Original list:
[1.1, 1, 0, -1, -1.1, 0.1]
After applying Recursive Insertion Sort:
[-1.1, -1, 0, 0.1, 1, 1.1]
