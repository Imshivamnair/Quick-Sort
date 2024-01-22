# Quick-Sort

Programmatic Approach for Quick Sort
First, create a recursive function that takes array, low value and high value as input and calls the partition fucntion for recursive call for partitioned arrays.
Define a partition function for last element as pivot and give the partition index of array.
Partition function iterate the given array and compare elements to pivot. If smallar then swap them to a sequential postion else no swap is performed.
At the end for iteration the pivot element is swapped to its correct position stored in i for the exact place.
Now return the latest position of the pivot element

Example: Here is the complete code for the Quick Sort algorithm using JavaScript:-

function partition(arr, low, high) { 
	let pivot = arr[high]; 
	let i = low - 1; 

	for (let j = low; j <= high - 1; j++) { 
		// If current element is smaller than the pivot 
		if (arr[j] < pivot) { 
			// Increment index of smaller element 
			i++; 
			// Swap elements 
			[arr[i], arr[j]] = [arr[j], arr[i]]; 
		} 
	} 
	// Swap pivot to its correct position 
	[arr[i + 1], arr[high]] = [arr[high], arr[i + 1]]; 
	return i + 1; // Return the partition index 
} 

function quickSort(arr, low, high) { 
	if (low >= high) return; 
	let pi = partition(arr, low, high); 

	quickSort(arr, low, pi - 1); 
	quickSort(arr, pi + 1, high); 
} 

let arr = [10, 80, 30, 90, 40]; 
console.log("Original array: " + arr); 

quickSort(arr, 0, arr.length - 1); 
console.log("Sorted array: " + arr);

Output :-
Original array: 10,80,30,90,40
Sorted array: 10,30,40,80,90

**Conclusion**

Quick sort is simple and easily implementable sorting technique that works on the divide and conquer approach. It is efficient for working on large dataset.

Time complexity of quickk sort is O(N log(N)) and auxiilary space required is O(N).
