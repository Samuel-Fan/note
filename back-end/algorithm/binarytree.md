# binarytree

由於自己有點不懂，先把想到的東西寫下來

## 試證明陣列第n項之child分別為2n+1、2n+2:

暫時先用矩陣長度 (length) 表示，即從 1 到 n 項，而非  0到 n-1 項</br>
下圖將矩陣 [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,...,n] 排列成 complete binary tree</br>
其中 leaf 數量與矩陣長度 (arr.length) 的關係為：</br></br>
leaf: &ensp; &ensp; &ensp; &ensp;0 &ensp;1 &ensp;2 &ensp;3 &ensp;4 &ensp;n </br>
arr.length: 1 &ensp;3 &ensp;5 &ensp;7 &ensp;9 &ensp;2n+1  </br></br>
由於每多一個 leaf 就會多出2項，因此 leaf 與 arr.length 的關係式即 arr.length = leaf *2 +1
從圖中可得知 length = n 時，其分支(即第 n 個 leaf ) 所長出之 left child 及 right child 分別為 2n、2n+1

![binary_tree1](https://raw.githubusercontent.com/Samuel-Fan/photo/main/binary-tree-1.jpg )

若將表示方式從　length　改成　index　(從第　0　到第　n-1　項表示)，</br>
即 length = n => index = n-1 ， left child 2n => 2n-1 ， right chile 2n+1 => 2n </br>
此時將 n - 1 = k 代入後如下圖，第 n 個 leaf 的：</br></br>
parent node = k</br></br>
left child node = 2n - 1 = 2 (k+1) -1 = 2k + 1 </br></br>
right child node = 2n  = 2 (k+1) = 2k + 2 </br></br>
得證。

![binary_tree2](https://raw.githubusercontent.com/Samuel-Fan/photo/main/binary-tree-2.JPG)
