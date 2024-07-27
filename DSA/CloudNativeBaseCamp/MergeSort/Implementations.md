
C#:
```csharp
using System;

class Program {

  public static void mergeSort(int[] array, int start, int end){
    if(end <= start) return;
    
    int midpoint = (end + start) / 2;
        mergeSort(array, start, midpoint);
    mergeSort(array, midpoint + 1, end);
    merge(array, start, midpoint, end); 
  }
  
  public static void merge(int[] array, int start, int midpoint, int end){
    int i,j,k;
    int left_length = midpoint - start + 1;
    int right_length = end - midpoint;
        
    int[] left_array = new int[left_length];
    int[] right_array = new int[right_length];

    for(i=0; i < left_length; i++){
      left_array[i] = array[start + i];
    }
    for(j=0; j < right_length; j++){
      right_array[j] = array[midpoint + 1 + j];
    }
    
    i = 0;
    j = 0;
    k = start;
    while(i < left_length && j < right_length){
      if( left_array[i] <= right_array[j] ){
        array[k] = left_array[i];
        i++;
      } else {
        array[k] = right_array[j];
        j++;
      }
      k++;
    }

    while(i < left_length){
      array[k] = left_array[i];
      i++;
      k++;
    }
    while(j < right_length){
      array[k] = right_array[j];
      j++;
      k++;
    }    
  }
  
  public static void Main (string[] args) {
    int[] array = {8, 65, 9, 7, 3, 5,54};
    
    Console.WriteLine( String.Join(", ", array) );
    mergeSort(array, 0, array.Length -1);
    Console.WriteLine( String.Join(", ", array) );
    
  }
}
```
Python:
```python
def merge_sort(array, start, end):
  # Base case: if there is only one element or less in the array, return it
  if end <= start:
    return

  # Divide the array into two halves
  midpoint = (end + start) // 2
  merge_sort(array, start, midpoint)
  merge_sort(array, midpoint + 1, end)

  # Merge the two sorted halves
  merge(array, start, midpoint, end)


def merge(array, start, midpoint, end):
  left_length = midpoint - start + 1
  right_length = end - midpoint

  # Create new arrays to hold the left and right halves of the original array
  left_array = [0] * left_length
  right_array = [0] * right_length

  # Copy the left half of the original array into the left_array
  for i in range(left_length):
    left_array[i] = array[start + i]

  # Copy the right half of the original array into the right_array
  for j in range(right_length):
    right_array[j] = array[midpoint + 1 + j]

  # Merge the left and right halves into the original array
  i = j = 0
  k = start
  while i < left_length and j < right_length:
    if left_array[i] <= right_array[j]:
      array[k] = left_array[i]
      i += 1
    else:
      array[k] = right_array[j]
      j += 1
    k += 1

  # Copy any remaining elements from the left or right halves into the original array
  while i < left_length:
    array[k] = left_array[i]
    i += 1
    k += 1

  while j < right_length:
    array[k] = right_array[j]
    j += 1
    k += 1


# Main function
if __name__ == "__main__":
  array = [8, 65, 9, 7, 3, 5, 54]

  print(array)
  merge_sort(array, 0, len(array) - 1)
  print(array)

```
C++:
```cpp
#include <iostream>
using namespace std;

// Merge the two sub-arrays while moving the negative numbers to the right side
void merge(int array[], int start, int mid, int end) {
    // Find the lengths of the left and right sub-arrays
    int left_length = mid - start + 1;
    int right_length = end - mid;
    
    // Create two temporary arrays to hold the left and right sub-arrays
    int left_array[left_length];
    int right_array[right_length];
    
    // Copy the elements of the left and right sub-arrays from the main array to the temporary arrays
    for(int i=0; i < left_length; i++){
        left_array[i] = array[start + i];
    }
    for(int j=0; j < right_length; j++){
        right_array[j] = array[mid + 1 + j];
    }

    // Merge the two sub-arrays while moving the negative numbers to the right side
    int i =0, j =0, k = start;
    while(i < left_length && left_array[i] <= 0){
        array[k] = left_array[i];
        i++;
        k++;
    }
    while(j < right_length && right_array[j] <= 0){
        array[k] = right_array[j];
        j++;
        k++;
    }
    while(i < left_length){
        array[k] = left_array[i];
        i++;
        k++;
    }
    while(j < right_length){
        array[k] = right_array[j];
        j++;
        k++;
    }
}

// Recursively divide the array into two halves
void segregate(int array[], int start, int end) {
    if(end <= start) return;

    int mid = (end + start) / 2;
    segregate(array, start, mid);
    segregate(array, mid+1, end);
    merge(array, start, mid, end);
}

// Test the segregate function with an example array
int main() {
    int array[] = {6, -5, 12, 10, -9, -1};
    int size = sizeof(array)/sizeof(array[0]);

    // Print the original array
    cout << "Original array: ";
    for (int i = 0; i < size; i++) {
        cout << array[i] << " ";
    }
    cout << endl;

    // Segregate the array and print the segregated array
    segregate(array, 0, size - 1);
    cout << "Segregated array: ";
    for (int i = 0; i < size; i++) {
        cout << array[i] << " ";
    }
    cout << endl;

    return 0;
}

```