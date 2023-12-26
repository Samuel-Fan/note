# HTML/CSS note
###### 使用freeCodeCamp初學，把筆記整理在這裡
## CSS
###### 利用元素(element)及class屬性選擇目標，編輯格式

#### 屬性選擇器 (Attribute selectors)
```
<main>
      <section>
        <h1 class="flex">
            <span class="company"> AcmeWidgetCorp </span>
            <span> Balance Sheet </span>
            <span> Current </span>
        </h1>
      </section>
</main>
```
1. 直接選擇element
```
main {
```
2. 選擇只有特定屬性值(唯一)的element
```
h1[class="flex"] {
```
3. 選擇有特定屬性值(非唯一)的element
```
h1[class~="flex"]{
```
4. 排除特定屬性值
```
span:not(.company) {
```
5. 直接選擇class屬性，需加"."
```
.flex {
```
6. 選擇特定element容器中的特定class，空白鍵後直接加
```
h1 .company {
```
7. 選擇具特定element及特定屬性值的目標，跟上一個差別在不加空白鍵
```
h1.flex {
```
8. 第(index)幾個element(class)、首個、最後一個
```
span:nth-of-type(index) {
span:first-of-type {
span:last-of-type {
```

#### 單位

1. px : pixel 絕對單位
2. % : 相對於上一層的值
3. 相對字體寬度(也可用於padding、margin等) : 
* em : 1em = 上一層font-size之大小
* rem : 1rem = 最上層font-size之大小(通常是body)
4. 可視範圍大小 :
* vw : viewport width (100vw = 整個視窗寬度的比例，滿版不會有捲軸)
* vh : viewport height (100vh = 整個視窗高度的比例)
  
#### padding、margin、borden

1. padding : 元素內所有內容與元素自身的邊界間距

2. margin : 元素與元素之間的邊界間距

3. border : 元素最外層的邊界

![padding、margin、borden](https://raw.githubusercontent.com/Samuel-Fan/photo/main/border_padding_margin.png)

* box-sizing : content-box -> width/height = content width/height 

* box-sizing : border-box -> width/height = border + padding + content width/height

#### 文字

* font-size : 字體大小
* font-family : 字體種類
* text-align : left 靠左，right 靠右，center 置中，justify 左右對齊
* text-decoration : underline 底線 (可搭配 dotted, wavy, color等特效) 
* letter-space : 字元間距
* font-weight : 字體粗細 (100-900, 以100為單位共9種 , 400 = normal, 700 = bold)
* font-style : normal常規字體，italic斜體，oblique斜角(italic某些字體不適用時)
* overflow : 文字(元素)溢滿容器時，依以下設定表示：
  * visible : 可以看見文字超出去的部分
  * hidden : 隱藏超出去的部分
  * scroll : 新增捲軸
 
#### 圖片

* aspect-ratio : 長寬比
* object-fit : 決定圖片(元素)如何調整至鎖定大小的容器中
  * fill : 縮放到滿版(會變形)
  * contain : 長邊填充元素，維持長寬比(會有空白處)
  * cover : 維持長寬比，滿版，超出部分被截掉
  * none : 原尺寸

#### display 

* block : 區塊元素，撐滿容器，如\<div>預設值
* inline : 行內元素，與其他行內元素並排在同一列，由內容決定寬高，如\<span>預設
* inline-block: 行內區塊，以inline的方式呈現，但同時擁有block的屬性，可設定寬高
* **flex** : flex box，類似inline會並排在同一列，有雙軸(主軸、交錯軸)概念
  * flex-direction : 決定主軸方向，分為 row、row-reverse、column、column-reverse
  * justify-content : 主軸對齊，分為:
    
    * flex-start : 預設值，對齊主軸線最前端
    * flex-end : 對齊主軸線最終端
    * center : 對齊主軸線中央
    * space-around : 平均分配寬度和間距，小方塊與父容器之間的間隔是小方塊彼此間隔的一半
    * space-evenly : 平均分配寬度和間距，每個小方塊之間和與父容器之間擁有相同的間隔
    * space-between : 平均分配寬度，第一項和最後一項貼齊邊緣
      
  * align-items : 對其交錯軸，分為:
    * flex-start : 對齊交錯軸線最前端
    * flex-end : 對齊交錯軸線最末端
    * center : 對齊交錯軸線中央
    * stretch : 預設值，將內容元素撐開至 flexbox 大小
    * baseline : 對齊內容物(文字)的基線

  * place-items : 同時設定 justify-content 及 align-items

  * flex-wrap : 內元件排列後，超過外容器主軸時的表現，分為:
    * nowrap : 讓元件超出去
    * wrap : 換行
    * wrap-reverse : 往反方向換行

* **grid** : 網格排列，有列(row)、行(column)概念
  * justify-content : 同flex的用法
  * align-items : 同flex的用法
  * grid-template-columns(rows):
    * 1fr 500px 1fr -> 分成3格，中間為500px，其他兩個1:1分配
    * repeat(5,1fr) -> 分成5格，比例為1:1:1:1:1
  * column-width : 單一行寬度，會依容器總寬度分配行數
  * grid-column(rows): 開始的位置/結束的位置 (分3個行時，最左為 1，最右為 4 (或-1)
  * grid-auto-flow : row (以塞滿列優先，為預設選項) column (以塞滿行為優先)
  * column(row)-gap: 行、列間距
#### Media queries

根據裝置的不同來呈現不同畫面，如以下語法限制當畫面寬度在 1000 px 以內時，body 套用顏色：
```
@media (max-width: 1000px) {
  body {
  background : black;
}
```

#### 全域變數
宣告：
```
:root {
--var-name: color;
}
```
使用：
```
element {
background : var(--var-name);
}
```
#### 位置 
* position : 決定元素的位置
  * static : 取消定位特性
  * relative : 相對位置，可設top, bottom, left, right值使其偏移
  * absolute : 絕對位置，不與其他元素排列，自己獨立一層
  * fixed : 決對位置，獨立一層，會黏在畫面上(類似甩不掉的廣告那種)
  * sticky : 畫面捲動時，會同時位移，效果只限上一層容器
* z-index : 在有設position的情況下，z-index高的在上面
  
#### 游標
```
.class:hover {
color : white; 
cursor : pointer;
}
```

#### 漸層
顏色漸層，語法如下：</br></br>
linear-gradient : 單方向
90deg => 左到右，</br>
0\~10% => color 1 單色</br>
10\~15% => color1 ~ color2漸層</br>
repeating : 重複至填滿100%</br></br>
radial-gradient : 輻射狀</br>
```
element{
background: repeating-linear-gradient(
      90deg,
      color1,
      color1 10%,
      color2 15%
    ), radial-gradient(
      color1 ,
      color 2)
)
}
```

半透明背景
```
body {
  color:black;
  background:linear-gradient(rgba(255,255,255,0.80), rgba(255,255,255,0.9)), url(...);
}
```
#### 動畫
語法(設定 0 ~ 100 % 特性)：
```
@keyframes name {
//初始條件
  0% {
    color: green;
  }
//結束條件
  100% {
    color: green;
}
}
```
在相對應的CSS元素中，相關屬性如下：
  * animation-name : 輸入keyframes name 產生連結
  * animation-duration : 持續時間
  * animation-iteration-count: 重複次數
  * animation-timing-function :
    * linear : 線性動作
    * ease-in-out : 初始、結束時較緩慢
可一次性設定相關屬性，如
```
animation : name 10s(duration) ease-in-out(timing-function) infinite(count);
```

##### 限sr(screen-reader)only
```
//暫時不懂，晚點再研究
//有!important 不會被其他設定蓋掉
span[class~="sr-only"] {
  border: 0 !important;
  clip: rect(1px, 1px, 1px, 1px) ;
  clip-path: inset(50%) ;
  height: 1px ;
  width: 1px ;
  position: absolute ;
  overflow: hidden ;
  white-space: nowrap ;
  padding: 0 ;
  margin: -1px ;
}
```
