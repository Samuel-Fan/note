# HTML/CSS note
###### 使用freeCodeCamp初學，把筆記整理在這裡
## HTML
### 結構，由各種元素(element)組成：

1. \<!DOCTYPE lang="HTML"> 宣告 : Document Type 的縮寫，意思是文件類型，告訴瀏覽器本頁面由 HTML5 編成。 
2. \<html> : HTML文檔的根/頂級(root)元素，包含所有其他的HTML元素。
3. \<head> : 不會顯示在瀏覽器上的部分，存放metadata(描述資料的資料)的地方，內容給「機器」運作、搜尋用的。
4. \<body> : 呈現給「使用者」看的東西都寫在這。
### \<html>
可加全域屬性(Global attributes)語言lang，用以告訴搜尋引擎判斷網頁內容，不會影響網頁呈現，常用：
   * 英文網站：  \<html lang="en">
   * 繁體中文網站：  \<html lang="zh-Hant-TW">

### \<head>  
##### 常用元素：

* \<title> : 網頁只能有一個標題，裡面的內容會顯示在書籤頁。
  
* \<metas> : self-closing(不需要結尾標籤)，常用的如：
  ```
  <meta charset="UTF-8">
  <meta name="description" content="網頁簡短描述">
  <meta name="keywords" content="網頁關鍵字">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  ```
  各項屬性如：
  * charset : 告訴瀏覽器這個網頁所用的編碼方式。
     
  * description : 用來寫網頁的簡短描述。
     
  * keywords : 網頁關鍵字。
     
  * viewport : 設計手機行動版網頁或響應式(RWD, Responsive Web Design) 網頁時，定義畫面：
     *  width=device-width 指定瀏覽器頁面的寬度同裝置 (device) 的寬度
     *  initial-scale=1.0 指定畫面初始縮放比例為 100%，即不放大也不縮小
     *  minimum-scale=1, maximum-scale=1"　可防止縮放
        
* \<link> : 可以用來載入或定義網頁中會用到的資源 (resource)，如：
  ```
  <link rel="stylesheet" href="styles.css" >
  ```
* \<style> : 可用CSS語法來設計網頁外觀。

### \<body>   

#### 文字、圖片：

**\<h1>-\<h6>** : 標題 (heading)，數字越小重要性越高

**\<p>** ： 文字段落 (paragraph)

**\<div>** : 包裹文字的容器，性質為 block (會換行) 
  * 區塊元素(block) : 元素寬度預設會撐到最大，使其占滿整個容器，可以設定長寬/margin/padding，但仍會占滿一整行
  
**\<span>** : 包裹文字的容器，性質為 inline (同一行) 容器
  * 行內元素(inline) : 圖片或文字均不換行，也不會影響其版面配置，不可設定長寬，元素的寬高由它的內容撐開
  * 行內區塊(inline-block) : 以inline的方式呈現，但同時擁有block的屬性，可設定元素的寬高/margin/padding，可水平排列

**\<img>** : 嵌入圖片，重要屬性如：

* src : 指定圖片url，為必要的屬性

* alt : 如圖片無法顯示時，會顯示的替代文字

* title : 滑鼠滑過圖片時，會顯示的文字 

#### 區塊：

**\<header>** : 標題區塊

**\<main>** : 放頁面主要資訊的區塊，每個頁面中只能有一個 \<main>

**\<section>** : 用在有明顯含義的區塊，一般會有自己的標題\<h1-6>，如無含義應使用\<div>

**\<article>** : 與\<section>相似，但內容更獨立且完整，可能是一篇文章、一則留言，或像論壇中的一個回覆

**\<nav>** : 導航區塊(navigation)，可透過設置連結前往網頁中的特定區塊，相關寫法如：
```
     <nav>
        <ul>
          <li><a href="#(id)">INFO</a></li>
          <li><a href="#(id)">HTML</a></li>
          <li><a href="#(id)">CSS</a></li>
        </ul>
      </nav>
```
**\<a>** : 建立超連結，例：
```
<a href="https://github.com/Samuel-Fan/note/edit/main/HTML.md">
```
#### 序列：

**\<ul>** : unordered list，無序列表，包裹\<li>

**\<ol>** : oredered list，有序列表，包裹\<li>

#### 表單：

**\<form>** : 建立表單，重要屬性如：

* action : 指定使用者送出表單後，送到的位址URL
  
* method : 指定資料傳輸時用的 HTTP 協議，分為"get"或"post"
  * get : 通常用在資料量較小或非敏感的資料，因為資料會被放在網址中直接傳出，容易被直接看到資料
  * post : 用在表單資料量比較大、有夾帶檔案上傳 (file upload) 或隱私性考量的資料

**\<fieldset>** : 對表單內控制元素件進行分組，\<legend> 標籤通常是\<fieldset> 裡面的第一個元素作為該分組的標題

**\<label>** : 用來給表單的控制元件一個說明標題，可搭配input, textarea, select等...

**\<input>** : 不需要closing tag，重要屬性如：

* name : 指定送出去的該筆資料要用什麼名稱，目的是讓遠端伺服器透過明確定義好的名稱去取出對應的欄位值
  
* type : 規定\<input>元素的類型，如text, email, radio(單選), checkbox(複選), date, number, password, file...

* pattern : 使用text, email, password...等等時，可控制輸入類型的屬性: [字符限制]{字數限制}

* placeholder : 預設顯示文字

* required : 必填

* checked : 預設勾選

input type = "radio" 例子：
```
// 同 "name" 屬性之情況下擇一 //
<label for="personal-account">
  <input id="personal-account" type="radio" name="account-type" checked > Personal
</label>
<label for="business-account">
  <input id="business-account" type="radio" name="account-type" > Business
</label>
```
input type ="password" 例子：
```
<label for="new-password"> Create a New Password:
  <input id="new-password" name="new-password" type="password" pattern="[a-z0-5]{8,}" required />
</label>
```
**\<textarea>** : 可輸入多行文字的輸入框，屬性如：

* rows : 設定高是幾行，預設為 2
  
* cols : 設定寬度，預設為 20 

**\<select>** : 下拉式選單，搭配＼<option>

**\<option>** : 如無value屬性，則預設輸出名稱為 option 的內容

#### 表格：

**\<table>** : 用來呈現二維的資料表資訊，作為以下元素的容器

**\<caption>** : 用來表示表格的標題

**\<thead>** : 用來表示表格中不同直行 (column) 的標題

**\<tbody>** : 做為表格主要內容的容器

**\<tr>** : 表格的橫列 (row)

**\<td>** : 表格的直行 (cloumn) 

**\<th>** : 欄位標題(table header)，\<th> 可用來替代 \<td> 使用，用來在語意上更明確的聲明這一格是一個標題

###### 註:每個 \<tr> 裡面的 \<td> (\<th>) 數量要一樣，才會組成一個格子狀的表格
