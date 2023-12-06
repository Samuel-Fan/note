# Sorting

## 目錄
* bubble sort
* insertion sort
* selection sort
* merge sort 
* heap sort
  
## 高時間複雜度的sorting方法
* bubble sort
* insertion sort
* selection sort<br />
### bubble sort <br />
從最右邊兩項開始，比較後排序，逐漸往左到最左邊兩項，如：<br />
５｜４｜１｜６｜３｜２  &emsp;-->&emsp;  ５ | ４ | １ | ６ | ２ | ３ &emsp;-->&emsp; ５ | ４ | １ | ２ | ６ | ３ -->&emsp; ５ | １ | ４ | ２ | ６ | ３<br />
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; ↑&emsp;&ensp;↑&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; &emsp;&ensp; ↑&emsp; ↑ &emsp;&emsp;&emsp; &emsp;&emsp;&emsp; &emsp; &emsp; &ensp;↑&emsp; ↑ <br /><br />
最後會變成 １ | ５ | ４ | ２ | ６ | ３ <br /><br />
此時最左邊的數字(1)已完成排序，右邊五項數字再進行同樣排序法 <br />
時間複雜度 = O(n<sup>2</sup>)<br />
### insertion sort <br />
從第1項(index = 1)開始，往左插入至已排序的序列，如：<br />
**４**｜１｜２｜６｜５｜３  &emsp;-->&emsp;  **１ | ４** | ２ | ６ | ５ | ３ &emsp;-->&emsp; **１ | ２ | ４** | ６ | ５ | ３ <br />
&emsp;&emsp; ↑ &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;　 ↑<br /><br />

最後會變成 １ | ２ | ３ | ４ | ５ | ６ 完成排序<br />
時間複雜度 = O(n<sup>2</sup>)<br />
### selection sort <br />
從第0項(index = 0)開始，找尋陣列中最小的數，將其與第0位交換，如：<br />
４｜１｜３｜６｜５｜２  &emsp;-->&emsp;  **１** | ４ | ３ | ６ | ５ | ２ &emsp;-->&emsp; **１ | ２** | ３ | ６ | ５ | ４ <br />
&emsp;&emsp; ↑ 最小值&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;&ensp;　 ↑最小值<br /><br />

最後會變成 １ | ２ | ３ | ４ | ５ | ６ 完成排序<br />
時間複雜度 = O(n<sup>2</sup>)<br />

## 低時間複雜度的sorting方法
* merge sort
* heap sort
### merge sort <br />
將長度為n之矩陣一分為二，直到變成n個長度為1的陣列，
此時將陣列兩兩依大小排列合併，成為n/2個長度為2的陣列(共計算n次)，
重複上述方法，直到矩陣還原成長度為n之排序矩陣(共計算n*log<sub>2</sub>n次)，
因此時間複雜度為O(nlogn)。
註:此方法空間複雜度較高。
```
function merge(arr1,arr2){
  let i = 0;
  let j = 0;
  let arr = [];
  while(i<arr1.length && j<arr2.length) {
    if (arr1[i]>arr2[j]){
      arr.push(arr2[j]);
      j++;
    } else {
      arr.push(arr1[i]);
      i++;
    }
  }
  while(i<arr1.length) {
    arr.push(arr1[i]);
    i++;
  }
  while(j<arr2.length){
    arr.push(arr2[j]);
    j++;

  }
  return arr;
}

function mergeSort(arr){
  if (arr.length === 1) {
    return arr;
  } else {
    let middle = Math.floor(arr.length / 2 );
    let left = arr.slice(0,middle);
    let right = arr.slice(middle);
    return merge(mergeSort(left),mergeSort(right));
  }
}
```
### heap sort 
```
let heapSize = arr.length - 1



function buildMaxHeap(){
  for (let i = Math.floor(heapSize/2); i>=0 ; i--){
    maxHeapify(i);
  }
}

function maxHeapify(i) {
  let l = 2 * i + 1 ;
  let r = 2 * i + 2 ;
  let largest;
  if (l <= heapSize && arr[l] > arr[i]){
    largest = l;
  } else {
    largest = i;
  }
  if (r <= heapSize && arr[r] > arr[largest]){
    largest = r;
  }
  if (largest !== i) {
    let temp = arr[i]; 
    arr[i] = arr[largest]; 
    arr[largest] = temp; 
    maxHeapify(largest);
  }
}

function heapSort(arr){
    buildMaxHeap();
    for (let i = heapSize; i>=0; i--){
      let temp = arr[0];
      arr[0] = arr[heapSize];
      arr[heapSize] = temp;
      heapSize--;
      buildMaxHeap();
    }
}
heapSort(arr);
console.log(arr);
```
