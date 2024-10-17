# Sorting algorithms
# Aim:
To study and implement Sorting Algorithm
     i) Selection Sort  ii) Insertion Sort   iii) Bubble Sort
## Theory:

#### 1. Selection sort 
Selection sort is a simple comparison-based sorting algorithm where the list is divided into two parts: a sorted part and an unsorted part. The smallest (or largest) element from the unsorted part is selected and swapped with the first unsorted element, growing the sorted part one element at a time.
* Working:
In each iteration, the algorithm searches for the smallest element in the unsorted portion of the list and swaps it with the element at the current position.

* Advantages:
-Simple to implement.
-Performs well on small datasets.
* Disadvantages:
-Inefficient for large datasets compared to more advanced algorithms like quicksort or mergesort.
-Does not adapt to already sorted lists.

![image](https://github.com/user-attachments/assets/1dd78916-f1d0-4cb7-bc7b-5aefccde1151)

### Code:
* Algorithm:
1. Take the input array and the number of elements.
2. Initialize an index n = 0.
3. Loop through the array (from start to the last unsorted element).
4. Inside the loop, set a pointer b to point to the next element after the current one.
5. Compare the current element with the next elements.
6. If any element is smaller than the current one, swap them.
7. Move to the next element by incrementing n and a.
8. Repeat the process until the array is fully sorted

#### Program:
```
//Priti
//230701230103
//selection sort 
#include<iostream>
using namespace std;
void swap(int*a, int *b)
{
    int temp;
    temp=*a;
    *a=*b;
    *b=temp;
}
void s_sort(int *a, int elements){
    int n=0;
    int *b;
    while (n!=elements)
    {
        b=a+1;
        for(int i=0; i<(elements-1)-n;i++){
            if(*a>*b){
                swap(a,b);
            }
            b++;
        }
        n++;
        a++;
    }
}
int main()
{
    int no_el;
    cout<<"How many elements in your array?"<<endl;
    cin>>no_el;
    int arr[no_el];
    cout<<"enter elements of array"<<endl;
    for(int i=0;i<no_el;i++)
    {
        cin>>arr[i];
    }
    cout<<"Sorted array"<<endl;
    s_sort(arr,no_el);
    for(int i=0;i<no_el;i++)
    {
        cout<<arr[i]<<" ";
    }
    return 0;
}
```
### Output:
![image](https://github.com/user-attachments/assets/fc77317b-b329-4199-9b82-9ad9a97e510e)


#### 2. Insertion sort 
Insertion sort builds a sorted array (or list) one element at a time. It takes each element from the input and inserts it into its correct position in the already sorted part of the list.

* Working:
The algorithm maintains a growing sorted portion of the list. For each element, it is compared to the elements in the sorted portion, and it is inserted in the correct position by shifting the other elements.

![image](https://github.com/user-attachments/assets/c010041c-d9d5-4081-b133-560e72dd5c09)

* Advantages:
1. Efficient for small datasets.
2. Performs well on datasets that are already partially sorted.
3. Simple to implement.
* Disadvantages:
1. Inefficient for large datasets.
### Code:
#### Algorithm:
1. Take the input array and the number of elements.
2. Loop through the array starting from the second element.
3. Set the current element as the key and j as the previous element's index.
4. Compare the key with the elements before it.
5. Shift all larger elements to the right.
6. Insert the key in its correct position.
7. Repeat this process for each element until the array is sorted.
#### Program:
```
//priti
//23070123103
//insertion sort 
#include<iostream>
using namespace std;
void insertionSort(int arr[],int n)
{
    for(int i=1;i<n;i++)
    {
        int key= arr[i];
        int j=i-1;
        while (j>=0 && arr[j]>key){
            arr[j+1]=arr[j];
            j--;
        }
        arr[j+1]=key;
    }
}
int main()
{
   int arr[]={64,25,12,22,11};
   int n= sizeof(arr)/sizeof(arr[0]);
   cout<<"Original array: "<<endl;
   for(int i=0;i<n;i++){
   cout<<arr[i]<<" "; }
   insertionSort(arr,n);
   cout<<"Sorted array: "<<endl;
   for(int i=0;i<n;i++){
   cout<<arr[i]<<" "; }
   return 0;
}
```
### Output:
![image](https://github.com/user-attachments/assets/fff7f6eb-ca5f-44db-a373-b1996aac920f)

#### 3. Bubble shot
Bubble sort is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. The process is repeated until the list is sorted.

* Working:
In each pass through the list, the largest unsorted element "bubbles up" to its correct position. The algorithm makes multiple passes, and after each pass, the next largest element is placed in its correct position.
* Advantages:
1. Simple to understand and implement.
2. Useful for small datasets.
* Disadvantages:
1. Inefficient for large datasets.

![image](https://github.com/user-attachments/assets/01a4696b-7c64-4bde-bd2b-9626316682dc)

### Code:
#### Algorithm:
1. Take the input array and the number of elements.
2. Initialize n = 0 to track the number of sorted elements.
3. Loop through the array, comparing each element with the next.
4. If the current element is greater than the next, swap them.
5. After each pass, the largest element bubbles to its correct position.
6. Increment n to exclude the already sorted elements.
7. Repeat the process until the entire array is sorted.

#### Program:
```
//Priti
//23070123103
//bubble sort 
# include<iostream>
using namespace std;

void swap(int* a,int* b){
    int temp;
    temp=*a;
    *a=*b;
    *b=temp;
}
int main(){
    int elements;
    cout<<"How many elements in the array? :";
    cin>>elements;
    int array[elements];
    cout<<"Enter elements:";
    for(int i=0;i<elements;i++){
        cin>>array[i];
    }
    for(int i=0;i<elements;i++){
        cout<<array[i]<<" ";
    }
    int n=0;
    while(n!=elements){
        for(int i=0;i<elements-n;i++){
            if(array[i]>array[i+1]){
                swap(&array[i],&array[i+1]);
            }
        }
        n++;
    }
    cout<<"\nSorted array is:"<<endl;
    for(int i=0;i<elements;i++){
        cout<<array[i]<<" ";
    }
    return 0;
}
```
### Output:
![image](https://github.com/user-attachments/assets/80d118e1-f8f2-4236-9036-749c46fb08f1)


## Conclusion:
We learnt about sorting algorithms : Selection sort, bubble sort and insertion sort. 
