# Sorting Algorithms  

A collection of classic sorting algorithms implemented in C++, with complexity analysis for each.

---

## Table of Contents

- [Selection Sort](#selection-sort)
- [Bubble Sort](#bubble-sort)
- [Insertion Sort](#insertion-sort)
- [Quick Sort](#quick-sort)
- [Complexity Comparison](#complexity-comparison)

---

## Selection Sort

> Finds the minimum element repeatedly and places it at the beginning.

| Complexity | Value |
|------------|-------|
| Space      | O(1)  |
| Average    | O(n²) |
| Worst      | O(n²) |

```cpp
#include <iostream>
using namespace std;

void swap(int &a, int &b)
{
    int temp = a;
    a = b;
    b = temp;
}

void SelectionSort(int arr[], int size)
{
    int minIdx;
    for (int i = 0; i < size - 1; i++)
    {
        minIdx = i;
        for (int j = i + 1; j < size; j++)
        {
            if (arr[j] < arr[minIdx])
                minIdx = j;
        }
        swap(arr[minIdx], arr[i]);
    }

    for (int i = 0; i < size; i++)
        cout << arr[i] << " ";
}

int main()
{
    int arr[] = {22, 10, 15, 3, 8, 20, 32, 11, 25, 5};
    int n = sizeof(arr) / sizeof(arr[0]);
    SelectionSort(arr, n);
    return 0;
}
```

---

## Bubble Sort

> Repeatedly swaps adjacent elements if they are in the wrong order.

| Complexity | Value |
|------------|-------|
| Space      | O(1)  |
| Best       | O(n)  *(already sorted)* |
| Average    | O(n²) |
| Worst      | O(n²) |

```cpp
#include <iostream>
using namespace std;

void BubbleSort(int arr[], int size)
{
    for (int i = 0; i < size - 1; i++)
    {
        bool swapped = false;
        for (int j = 0; j < size - i - 1; j++)
        {
            if (arr[j] > arr[j + 1])
            {
                swap(arr[j], arr[j + 1]);
                swapped = true;
            }
        }
        if (!swapped) break; 
    }

    for (int i = 0; i < size; i++)
        cout << arr[i] << " ";
}

int main()
{
    int arr[] = {22, 10, 15, 3, 8, 20, 32, 11, 25, 5};
    int n = sizeof(arr) / sizeof(arr[0]);
    BubbleSort(arr, n);
    return 0;
}
```

---

## Insertion Sort

> Builds the sorted array one element at a time by inserting each into its correct position.

| Complexity | Value |
|------------|-------|
| Space      | O(1)  |
| Best       | O(n)  *(already sorted)* |
| Average    | O(n²) |
| Worst      | O(n²) |

```cpp
#include <iostream>
using namespace std;

void InsertionSort(int arr[], int size)
{
    for (int i = 1; i < size; i++)
    {
        int key = arr[i];
        int j = i - 1;

        while (j >= 0 && arr[j] > key)
        {
            arr[j + 1] = arr[j]; 
            j--;
        }
        arr[j + 1] = key; 
    }

    for (int i = 0; i < size; i++)
        cout << arr[i] << " ";
}

int main()
{
    int arr[] = {22, 10, 15, 3, 8, 20, 32, 11, 25, 5};
    int n = sizeof(arr) / sizeof(arr[0]);
    InsertionSort(arr, n);
    return 0;
}
```

---

## Quick Sort

> Divides the array around a pivot, recursively sorting each partition.

| Complexity | Value |
|------------|-------|
| Space      | O(log n) |
| Best       | O(n log n) |
| Average    | O(n log n) |
| Worst      | O(n²) *(already sorted or reverse sorted)* |

```cpp
#include <iostream>
using namespace std;

int Partition(int arr[], int low, int high)
{
    int pivot = arr[high]; // Last element as pivot
    int i = low - 1;       // i points to last element smaller than pivot

    for (int j = low; j < high; j++)
    {
        if (arr[j] <= pivot)
        {
            i++;
            swap(arr[i], arr[j]); //
        }
    }
    swap(arr[i + 1], arr[high]); 
    return i + 1;
}

void QuickSort(int arr[], int low, int high)
{
    if (low < high)
    {
        int pivotIdx = Partition(arr, low, high);
        QuickSort(arr, low, pivotIdx - 1);  
        QuickSort(arr, pivotIdx + 1, high); 
    }
}

int main()
{
    int arr[] = {22, 10, 15, 3, 8, 20, 32, 11, 25, 5};
    int n = sizeof(arr) / sizeof(arr[0]);
    QuickSort(arr, 0, n - 1);

    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";

    return 0;
}
```

---

## Complexity Comparison

| Algorithm      | Best       | Average    | Worst      | Space    | Stable |
|----------------|------------|------------|------------|----------|--------|
| Selection Sort | O(n²)      | O(n²)      | O(n²)      | O(1)     | No     |
| Bubble Sort    | O(n)       | O(n²)      | O(n²)      | O(1)     | Yes    |
| Insertion Sort | O(n)       | O(n²)      | O(n²)      | O(1)     | Yes    |
| Quick Sort     | O(n log n) | O(n log n) | O(n²)      | O(log n) | No     |

> **Stable** means equal elements maintain their original relative order after sorting.

---

## Test Input

All algorithms are tested with the same array:

```
{22, 10, 15, 3, 8, 20, 32, 11, 25, 5}
```

Expected output:

```
3 5 8 10 11 15 20 22 25 32
```
