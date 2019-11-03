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

        <ion-slide>
          <h1>Slide 3</h1>
        </ion-slide>
    </ion-slides>

我們只要這份 code 放到我們需要的地方，便可以直接使用



