# HTML/CSS note
###### 使用freeCodeCamp初學，把筆記整理在這裡
## HTML
### 結構，由各種元素(element)組成：

1. \<!DOCTYPE lang="HTML"> 宣告 : Document Type 的縮寫，意思是文件類型，告訴瀏覽器本頁面由 HTML5 編成。 
2. \<html> : HTML文檔的根/頂級(root)元素，包含所有其他的HTML元素。
3. \<head> : 不會顯示在瀏覽器上的部分，存放metadata(描述資料的資料)的地方，內容給「機器」運作、搜尋用的。
4. \<body> : 呈現給「使用者」看的東西都寫在這。
### \<html\>
可加全域屬性(Global attributes)語言lang，用以告訴搜尋引擎判斷網頁內容，不會影響網頁呈現，常用：
   * 英文網站：  \<html lang="en">
   * 繁體中文網站：  \<html lang="zh-Hant-TW">

### \<head\>  
##### 常用元素：
* \<title> : 網頁只能有一個標題，裡面的內容會顯示在書籤頁。
* \<metas> : self-closing(不需要結尾標籤)，常用的：
  1. \<meta charset="UTF-8"> : 告訴瀏覽器這個網頁所用的編碼方式。
  2. \<meta name="description" content="網頁簡短描述"> : 用來寫網頁的簡短描述。
  3. \<meta name="keywords" content="網頁關鍵字"> : 網頁關鍵字。
  4. \<meta name="viewport" content="width=device-width, initial-scale=1.0" />
* \<link>
* \<style> : 用CSS取代比較好。
