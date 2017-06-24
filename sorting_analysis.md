# Analysis of sorting algorithms
Analyzing the general approach and performance of major sorting algorithms, and how to spot them.

#### Spotting algorithms

    Given you have an unsorted array of integers written in the form `a[0] a[1] a[2] ... a[n]`, with the goal to sort them in ascending order, for example `1 3 4 77 454 ...`. Indicate positional changes of every element compared with the current, partially sorted version, with arrows.


##### Bubble sort

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
    The original array is sufficient, plus one temp variable that is used to save one value when swapping cells.

##### Insertion sort

    


#### Performance
##### Theoretical limits
The theoretical upper speed limit for sorting a set with the length `n` of comparable objects, ie an array with integers, is `O(n*log(n))`. Take a selection sort with a random dataset:

First, all values are put into a heap, and then, `removeMin()` is called `n` times. Since after every `removeMin()`, restructuring in form of down-bubbling could be necessary, in the worst case bubbling to the very bottom, every of the `n` `removeMin()` takes about `log(n)` ( == `height`) time.

Thus the theoretical upper speed bound for sorting `n` elements is `n*log(n)`

##### Practical limits
There is no sorting algorithm perfect for every arbitrary data set. Worst-case scenarios are rarely worth considering, given the data sets are not expected to be heterogeneous or significantly pre-sorted..
