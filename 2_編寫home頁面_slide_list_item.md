## 如何開始 coding ?

在這裡我們使用 [VS code](https://code.visualstudio.com/) 來做編寫程式\
在cmd中輸入

    code .

就會將整個檔案資料夾匯入 VS code 中

## Home Page

我們可以在 **src/app/home/** 中找到 home.page.html 、 home.page.scss ...

![image](教程圖片/1572784367774.jpg)

在 home.page.html 中，我們的 coding 方式就跟一般我們寫 html 一樣\
而在 home.page.scss 中，編寫的方式也是跟平常我們寫網頁的 css 一樣\
\
那我們為什麼要選擇使用 ionic 呢??\
**ionic** 不同的地方是，他有自己的一些[UI Components](https://ionicframework.com/docs/components)可以使用\
藉由這些UI元件，我們可以快速的完成許多功能


> **Slide**

在這裡因為我們頁面的需求，我們需要一個可以左右滑動的頁面\
在 ionic UI Components 中有個功能是 [ion-slides](https://ionicframework.com/docs/api/slides) 可以實現我們的需要

    <ion-slides pager="true">
        <ion-slide>
          <h1>Slide 1</h1>
        </ion-slide>

        <ion-slide>
          <h1>Slide 2</h1>
        </ion-slide>
    </ion-slides>

我們只要這份 code 放到我們需要的地方，便可以直接使用\
\
ionic UI Components 有個好處，每個 UI 都可以設定各種屬性和功能，來更加符合自己的需求\
\
**Properties** : 可以設定各種 ionic 定義的屬性，可以直接加在 **< >** 中\
Ex. 在 ion-slides 中加入 pager 屬性
    
    <ion-slides pager="true">

\
**Events** : 可以設定各種 ionic 定義的觸發事件，連動.ts 的 function ，也是可以直接加在 **< >** 中\
Ex.  在 ion-slides 中加入 ionSlideDidChange Events

     <ion-slides (ionSlideDidChange)="funtion()">

 

> **List & Item**

在這裡我們使用 [ion-list](https://ionicframework.com/docs/api/list) 和 [ion-item](https://ionicframework.com/docs/api/item) 來幫助我們列出每一台機台資訊

    <ion-list>
        <ion-item>
            <ion-label>1F-A</ion-label>
        </ion-item>
        <ion-item>
            <ion-label>1F-B</ion-label>
        </ion-item>
        <ion-item>
            <ion-label>2F-A</ion-label>
        </ion-item>
        <ion-item>
            <ion-label>2F-B</ion-label>
        </ion-item>
        <ion-item>
            <ion-label>3F-A</ion-label>
        </ion-item>
        <ion-item>
            <ion-label>3F-B</ion-label>
        </ion-item>
    </ion-list>

在完成以上教學，我們可以得到一個這樣的介面

<img src="教程圖片/1572839994496.jpg" width="300px" height="534px">

因為我們的 **slide** 介面沒有幫它設定寬度，所以就會擠成一塊\
這個時候，我們可以來編寫 CSS 讓我們的版面更好看\
\
我們可以在 **ion-list** 中加入 *style* 來加入我們 CSS code

     <ion-list style="width: 100%;">

\
或是我們也可以在 **html.page.scss** 中加入

    .list_style{
        width: 100%;
    }

然後再在 **html.page.html** 的 **ion-list** 中加入 *class*

    <ion-list class="list_style">

這樣我們就可以得到以下這個結果 ↓ ↓ ↓

<img src="教程圖片/1572841236822.jpg" width="300px" height="534px">




























