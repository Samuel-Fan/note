# Sorting

## 目錄
* bubble sort
* insertion sort
* selection sort

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
時間複雜度 = O(n2)<br />
### insertion sort <br />
從第1項(index = 1)開始，往左插入至已排序的序列，如：<br />
**４**｜１｜２｜６｜５｜３  &emsp;-->&emsp;  **１ | ４** | ２ | ６ | ５ | ３ &emsp;-->&emsp; **１ | ２ | ４** | ６ | ５ | ３ <br />
&emsp;&emsp; ↑ &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;　 ↑<br /><br />

最後會變成 １ | ２ | ３ | ４ | ５ | ６ 完成排序<br />
時間複雜度 = O(n2)<br />
### selection sort <br />
從第0項(index = 0)開始，找尋陣列中最小的數，將其與第0位交換，如：<br />
４｜１｜３｜６｜５｜２  &emsp;-->&emsp;  **１** | ４ | ３ | ６ | ５ | ２ &emsp;-->&emsp; **１ | ２** | ３ | ６ | ５ | ４ <br />
&emsp;&emsp; ↑ 最小值&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;&ensp;　 ↑最小值<br /><br />

最後會變成 １ | ２ | ３ | ４ | ５ | ６ 完成排序<br />
時間複雜度 = O(n2)<br />
