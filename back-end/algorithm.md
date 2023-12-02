以下筆記引用自Udemy上Wilson Ren老師之「資料結構與演算法 (JavaScript)」課程
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
題目:找arr中數字為n之值，
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
### counter
題目:從兩個arr中找到交集的數字，
時間複雜度由雙迴圈的 O(n2) 降為 O(n)
```
function intersection(n, m) {
  let arr1 = [];
  let arr2 = n.concat(m);
  // arr2 = [15, 3, 6, 8, 24, 16, 11, 3, 9, 6, 15, 8];
  let counter = {};
  for (let i = 0; i < arr2.length; i++) {
    // 初始時counter是空物件，!counter[arr2[i]]必定為true
    // 此時counter[arr2[i]] = 1 => counter["第一個值"] = 1 => counter = {"15" : 1}
    // object 屬性一律為字串，因此15 ==> "15"，1~9的數字會自動排序，如果是0開頭的屬性如001 002這種就不會自動排序了
    if (!counter[arr2[i]]) {
      counter[arr2[i]] = 1;
    } else {
      counter[arr2[i]]++;
    }
  }
  for (let property in counter) {
    if (counter[property] >= 2) {
      arr1.push(property);
    }
  }
  arr1.forEach((n, index) => (arr1[index] = Number(n))); //必要嗎?
  return arr1;
}

intersection([15, 3, 6, 8, 24, 16], [11, 3, 9, 6, 15, 8]);
```
### pointer
題目：找arr內平均值=avg的組合，
時間複雜度由雙迴圈的 O(n2) 降為 O(n)
```
//averagePair([-11,0,1,2,3,9,14,17,21],1.5);
let step = 0;
function averagePair(arr, avg) {
  let i = 0;
  let j = arr.length - 1;
  let result = [];
  while (i <= j) {
    if ((arr[i] + arr[j]) / 2 > avg) {
      j--;
      step++;
    } else if ((arr[i] + arr[j]) / 2 < avg) {
      i++;
      step++;
    } else if ((arr[i] + arr[j]) / 2 === avg) {
      result.push([arr[i], arr[j]]);
      i++;
      j--;
      step++;
    }
  }
  return result;
}

console.log(averagePair([-11, 0, 1, 2, 3, 9, 14, 17, 21], 1.5));
console.log(step);
```
