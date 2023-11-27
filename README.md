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

#### 文字類：

\<h1>-\<h6> : 標題 (heading)，數字越小重要性越高

\<p> ： 文字段落 (paragraph)

\<div> : 包裹文字的容器，性質為 block (會換行) 
  * 區塊元素(block) : 元素寬度預設會撐到最大，使其占滿整個容器，可以設定長寬/margin/padding，但仍會占滿一整行
  
\<span> : 包裹文字的容器，性質為 inline (同一行) 容器
  * 行內元素(inline) : 圖片或文字均不換行，也不會影響其版面配置，不可設定長寬，元素的寬高由它的內容撐開
  * 行內區塊(inline-block) : 以inline的方式呈現，但同時擁有block的屬性，可設定元素的寬高/margin/padding，可水平排列

#### 區塊類：

\<header> : 標題區塊

\<section> : 用在有明顯含義的區塊，一般會有自己的標題\<h1-6>，如無含義應使用\<div>

\<article> : 與\<section>相似，但內容更獨立且完整，可能是一篇文章、一則留言，或像論壇中的一個回覆

\<nav> : 導航區塊(navigation)，可透過設置連結前往網頁中的特定區塊，相關寫法如：
```
     <nav>
        <ul>
          <li><a href="#(id)">INFO</a></li>
          <li><a href="#(id)">HTML</a></li>
          <li><a href="#(id)">CSS</a></li>
        </ul>
      </nav>

```


