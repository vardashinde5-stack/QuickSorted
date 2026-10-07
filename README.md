# Experiment No. 2

## Title

**Quick Sort Using Divide and Conquer**

## Aim

To implement the Quick Sort algorithm using the Divide and Conquer technique and analyze its time and space complexity.

## Program

```c
#include <stdio.h> 
 
void quickSort(int a[], int low, int high) 
{ 
    int i, j, pivot, temp; 
 
    if (low < high) 
    { 
        pivot = a[low]; 
        i = low; 
        j = high; 
 
        while (i < j) 
        { 
            while (a[i] <= pivot && i < high) 
                i++; 
 
            while (a[j] > pivot) 
                j--; 
 
            if (i < j) 
            { 
                temp = a[i]; 
                a[i] = a[j]; 
                a[j] = temp; 
            } 
        } 
 
        temp = a[low]; 
        a[low] = a[j]; 
        a[j] = temp; 
 
        quickSort(a, low, j - 1); 
        quickSort(a, j + 1, high); 
    } 
} 
 
int main() 
{ 
    int a[50], n, i; 
 
    printf("Enter number of elements: "); 
    scanf("%d", &n); 
 
    printf("Enter elements:\n"); 
    for (i = 0; i < n; i++) 
        scanf("%d", &a[i]); 
 
    quickSort(a, 0, n - 1); 
 
    printf("Sorted elements are:\n"); 
    for (i = 0; i < n; i++) 
        printf("%d ", a[i]); 
 
    return 0; 
}
```

## Output

The terminal output of the Quick Sort program is shown below:

![Quick Sort Terminal Output](https://github.com/vardashinde5-stack/QuickSorted/blob/main/VS%20Code%20Terminal%20Quick%20Sort%20Output.png)

## Time Complexity

| Case         | Time Complexity |
| ------------ | --------------- |
| Best Case    | **O(n log n)**  |
| Average Case | **O(n log n)**  |
| Worst Case   | **O(n²)**       |

### Explanation

Quick Sort works using the **Divide and Conquer** technique.

1. A pivot element is selected from the array.
2. The array is partitioned around the pivot.
3. Elements smaller than or equal to the pivot are placed on one side.
4. Elements greater than the pivot are placed on the other side.
5. The same process is recursively applied to the two subarrays.

When the pivot divides the array into nearly equal parts, the time complexity is **O(n log n)**.

In the worst case, when the pivot produces highly unbalanced partitions, the time complexity becomes **O(n²)**.

## Space Complexity

Quick Sort is an in-place sorting algorithm because it does not require an additional array for sorting.

* **Average Space Complexity:** **O(log n)**
* **Worst Case Space Complexity:** **O(n)**

The space is mainly required for the recursive function call stack.

## Applications

1. Used for sorting arrays and datasets.
2. Useful when efficient in-place sorting is required.
3. Used in applications where average-case performance is important.
4. Commonly used in computer science and algorithm design.
5. Useful for sorting large collections of numerical or comparable data.
6. Forms the basis for understanding Divide and Conquer algorithms.

## Advantages

* Fast average-case performance.
* Requires no additional array for sorting.
* Efficient for large datasets in average cases.
* Uses the Divide and Conquer approach.

## Limitations

* Worst-case time complexity is **O(n²)**.
* Performance depends on the selection of the pivot.
* Recursive implementation requires stack space.

## Conclusion

Quick Sort is an efficient sorting algorithm based on the **Divide and Conquer** technique. It selects a pivot, partitions the array around the pivot, and recursively sorts the resulting subarrays.

The average and best-case time complexity of Quick Sort is **O(n log n)**, while its worst-case time complexity is **O(n²)**. The algorithm is generally efficient because it performs sorting in-place without requiring an additional array.

## GitHub Repository

[Quick Sort - GitHub](https://github.com/vardashinde5-stack/QuickSorted)

## Output Image

[Quick Sort Terminal Output](https://github.com/vardashinde5-stack/QuickSorted/blob/main/VS%20Code%20Terminal%20Quick%20Sort%20Output.png)
