## Selection Sort
- Space Complexity  = O(1)
- Average Case = O ($n^2$)
- Worst Case = O ($n^2$)
``` cpp
#include <iostream>   
using namespace std;  
  
void SelictionSort(int arr[], int size)  
{  
    int minIdx;  
    for (int i = 0; i < size - 1; i++)  
    {  
        minIdx = i;  
        for (int j = i + 1; j < size; j++)  
        {  
            if (arr[j] < arr[minIdx])  
            {  
                minIdx = j;  
            }  
        }  
        swap(arr[minIdx], arr[i]);  
    }  
    for (int i = 0; i < size; i++)  
    {  
        cout << arr[i] << " ";  
    }  
}  
  
void swap(int &a, int &b)  
{  
    int temp = a;  
    a = b;  
    b = temp;  
}  
  
  
  
int main()  
{  
    int arr[] = {22, 10, 15, 3, 8, 20, 32, 11, 25, 5};  
    int n = sizeof(arr) / sizeof(arr[0]);  
    SelictionSort(arr, n);  
  
    return 0;  
}
```
## Bubble Sort
- **Space Complexity** = O(1)
- **Best Case** = O(n) _(لو الـ array مرتبة خلاص)_
- **Average Case** = O(n²)
- **Worst Case** = O(n²)
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
    {
        cout << arr[i] << " ";
    }
}

int main()
{
    int arr[] = {22, 10, 15, 3, 8, 20, 32, 11, 25, 5};
    int n = sizeof(arr) / sizeof(arr[0]);
    BubbleSort(arr, n);
    return 0;
}
```
## Insertion Sort




