# Thinkful - Data Structures & Algorithms

Introduction module on data structures and algorithms including:

- Recursive Algorithms
- Big O Notation
- Working with Arrays
- Working with Linked Lists
- Working with Stacks and Queues
- Working with Hash maps
- Working with Binary Search Trees
- Search Algorithms
- **Sorting Algorithms** (current)

## Sorting Algorithms

### Bubble Sort - How not to do it!

```
function swap(array, i, j) {
    const tmp = array[i];
    array[i] = array[j];
    array[j] = tmp;
};

function bubbleSort(array) {
    let swaps = 0;
    for (let i = 0; i < array.length - 1; i++) {
        if (array[i] > array[i + 1]) {
            swap(array, i, i + 1);
            swaps++;
        }
    }

    if (swaps > 0) {
        return bubbleSort(array);
    }
    return array;
};
```

### Merge Sort

### Quick Sort

### Exercises
