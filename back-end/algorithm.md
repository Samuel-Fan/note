# Big O notation
## 定義
待補
## 複雜度(complecity)
越往下複雜度越高
* O(1)： Constant time
* O(log N)： Iterated logarithmic time
* O(N)： Linear time
* O(N log N)： Linearithmic time
* O(N²)： Quadratic time
* O(2^n)： Exponential time
* O(N!)： Factorial time
### binarySearch
時間複雜度由linearSearch 的 O(n) 降為 O(logn)
```
function binarySearch(arr, n) {
  let min = 0;
  let max = arr.length - 1;

// 將array分成兩半，直到arr[middle] == n //
// 若找不到 n ，則會形成min == max 的情形，下一步就會發生min>max，使迴圈停止 //

  while (min <= max) {
    let middle = Math.floor((max + min) / 2);
    if (n > arr[middle]) {
      min = middle + 1;
    } else if (n < arr[middle]) {
      max = middle - 1;
    } else if (n === arr[middle]) {
      return middle;
    }
  }
  console.log("Cannot find number " + n);
  return -1;
}
```
