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

**Big-O**

- Best case -> O(n)
- Average Case -> O(n^2)
- Worst case -> O(n^2)

### Merge Sort

```
function mergeSort(array) {
    if (array.length <= 1) {
        return array:
    }

    const middle = Math.floor(array.length /2);
    let left = array.slice(0, middle)
    let right = array.slice(middle, array.length);

    left = mergeSort(left)
    right = mergeSort(right)
    return merge(left, right, array);
}

function merge(left, right, array) {
    let leftIndex = 0;
    let rightIndex = 0;
    let outputIndex = 0;
    while (leftIndex < left.length && rightIndex < right.length) {
        if(left[leftIndex] < right[rightIndex]) {
            array[outputIndex++] = left[leftIndex++]
        } else {
            array[outputIndex++] = right[rightIndex++]
        }
    }
    for (let i = leftIndex; i < left.length; i++) {
        array[outputIndex++] = left[i]
    }
    for (let i = rightIndex; i < right.length; i++) {
        array[outputIndex++] = right[i]
    }
    return array;
}
```

**Big-O**

- Best case -> O(log(n))
- Average case -> O(log(n))
- Worst case -> O(log(n))

### Quick Sort

```
function quickSort(array, start = 0, end = array.length) {
    if (start >= end) {
        return array;
    }

    const middle = partition(array, start, end)
    array = quickSort(array, start, middle);
    array = quickSort(array, middle + 1, end);

    return array;
}

//Lomuto's partition algorithm

function partition(array, start, end) {
    const pivot = array[end - 1]
    let j = start;
    for (let i = start; i < end; i++) {
        if (array[i] <= pivot) {
            sway(array, i, j);
            j++
        }
    }
    swap(array, end-1, j);
    return j;
}
```

### Exercises
