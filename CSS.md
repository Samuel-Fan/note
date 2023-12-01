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

![padding、margin、borden](https://raw.githubusercontent.com/Samuel-Fan/photo/main/123.png)

* box-sizing : content-box -> width/height = content width/height 

* box-sizing : border-box -> width/height = border + padding + content width/height

#### 文字

* font-size : 字體大小
* font-family : 字體種類
* text-align : left 靠左，right 靠右，center 置中，justify 左右對齊
* letter-space : 字元間距
* font-weight : 字體粗細 (100-900, 以100為單位共9種 , 400 = normal, 700 = bold)
* font-style : normal常規字體，italic斜體，oblique斜角(italic某些字體不適用時)

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
    * space-around : 平均分配寬度和間距
    * space-between : 平均分配寬度，第一項和最後一項貼齊邊緣
      
  * align-items : 對其交錯軸，分為:
    * flex-start : 對齊交錯軸線最前端
    * flex-end : 對齊交錯軸線最末端
    * center : 對齊交錯軸線中央
    * stretch : 預設值，將內容元素撐開至 flexbox 大小
    * baseline : 對齊內容物(文字)的基線
   
  * flex-wrap : 內元件排列後，超過外容器主軸時的表現，分為:
    * nowrap : 讓元件超出去
    * wrap : 換行
    * wrap-reverse : 往反方向換行
    * 
