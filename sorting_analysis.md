# Analysis of sorting algorithms
Analyzing the general approach and performance of major sorting algorithms, and how to spot them.

## Spotting algorithms

Given you have an unsorted array of integers written in the form `a[0] a[1] a[2] ... a[n]`, with the goal to sort them in ascending order, for example `1 3 4 77 454 ...`. Indicate positional changes of every element compared with the current, partially sorted version, with arrows.


### Bubble sort

**Distinct features**

There is a quick and a slow direction. This is a very distinctive feature as you see (one runthrough from left to right):

`23 88 64 32 11`

`23 64 32 11 88`

The direction in which you run along is the fast direction. The biggest/smallest number (88) is guaranteed to show up (bubble up) at the very end after only 1 runthrough.

Into the opposite direction, every number can only progress 1 step at most per run.

**Signs of bubblesort:**

This means that bubble sort might show generally longer arrows into one direction (fast direction) than the other, with either the biggest or the smallest element at one end of the array.

**Signs of not bubblesort:**

Scout for the biggest and the smallest value. If they are both somewhere in between, it's not a bubblesort

**Smallest data structure to be used**

The original array is sufficient.

### Insertion sort
**Distinct features**

With insertion sort, there is a sorted and a unsorted part of the array. Starting at a[0] (one value is always sorted), the next right value in the array is then inserted at the right point in the sorted part of the array. The important part here is that from one end of the array, a sorted part "grows" by 1 each time, forcing the unsorted part back:

`[sorted part] unsorted part` :

`[7] 3 5 83 25 33`

`[3 7] 5 83 25 33`

`[3 5 7] 83 25 33`

`[3 5 7 83] 25 33`

**Signs of insertion sort**

One part of the array (either growing from left or right) is sorted, while the other one is either

(1) in its initial state and not changed (not using a heap), or

(2)representing a heap. The heap would have the smallest value at its first position, and then values "vaguely" sorted (look up the heap representation in an array for more info).

**Signs of not insertion sort**

If there is no section that is clearly sorted (this has to be the case, regardless of how the unsorted part is structured).

**Smallest data structure to be used**

Regardless of a heap is used to organize the unsorted pool (O(n * log(n))) or not (O(n²)), the original array is sufficient, since the heap doesn't take any more space than the unsorted values would do otherwise.

### Selection sort
**Distinctive features**




## Performance
### Theoretical limits
The theoretical upper speed limit for sorting a set with the length `n` of comparable objects, ie an array with integers, is `O(n*log(n))`. Take a selection sort with a random dataset:

First, all values are put into a heap, and then, `removeMin()` is called `n` times. Since after every `removeMin()`, restructuring in form of down-bubbling could be necessary, in the worst case bubbling to the very bottom, every of the `n` `removeMin()` takes about `log(n)` ( == `height`) time.

Thus the theoretical upper speed bound for sorting `n` elements is `n*log(n)`

#### Practical limits
There is no sorting algorithm perfect for every arbitrary data set. Worst-case scenarios are rarely worth considering, given the data sets are not expected to be heterogeneous or significantly pre-sorted..
