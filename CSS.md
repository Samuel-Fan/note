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
2. 選擇只有only特定屬性、特定屬性值的element
```
h1[class] {
h1[class="flex"] {
```
3. 選擇包含特定屬性的element
```
h1[class~="flex"]{
```
4. 直接選擇class屬性，需加"."
```
.flex {
```
5. 選擇特定element裡包含的特定class，空白鍵後直接加
```
main .flex {
```
6. 第(index)幾個element(class)、首個、最後一個
```
span:nth-of-type(index) {
span:first-of-type {
span:last-of-type {
```
7. 排除特定屬性值
```
span:not(.company) {
```
