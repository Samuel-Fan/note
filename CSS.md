# HTML/CSS note
###### 使用freeCodeCamp初學，把筆記整理在這裡
## CSS
###### 利用元素(element)及class屬性選擇目標，編輯格式

#### 屬性選擇器 (Attribute selectors)
```
<main>
      <section>
        <h1 class="flex">
            <span> AcmeWidgetCorp </span>
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
2. 選擇具特定class屬性的element
```
h1[class="flex"]{
```
3. 直接選擇class屬性，需加"."
```
.flex {
```
4. 選擇特定element裡的特定class，空白鍵後直接加
```
main .flex {
```
5. 第(index)幾個element(class)、首個、最後一個
```
span:nth-of-type(index) {
span:first-of-type {
span:last-of-type {
```
