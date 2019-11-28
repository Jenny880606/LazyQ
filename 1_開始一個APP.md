# ionic 環境
> 下載 Ionic

參考資料: [ionic 下載說明](https://ionicframework.com/docs/installation/cli)\
以下說明為windows版本，在cmd中輸入以下指令

* install the ionic CLI and Cordova

      npm install -g ionic cordova
    
    
> code editor

一般的 code editor 都可以用來編譯 ionic 的程式碼，在官網上提供了兩款他們推薦的編譯器\
在這裡，我們是使用 VS Code 來編譯我們的程式

* [Ionic Studion](https://ionicframework.com/studio?utm_source=docs&utm_medium=website&utm_campaign=studio%20launch)
* [VS Code](https://code.visualstudio.com/)



# 開始ionic專案
**( 小提醒 : 新專案的檔案位置和輸入cmd的資料夾是在同一個地方 )**
> start an app

*name* 是你這個專案的名稱\
*template* 是你個專案的版型，ionic有3種基本的版型 *blank*、*sidemenu*、*tabs*


    ionic start [<name>] [<template>]

在 LazyQ+ 中，我們是使用 *sidemenu* 這個版型作為基礎來修改

> run your APP

ionic 會在你的瀏覽器上顯示你現在這份APP的樣子

    cd [<name>]
    ionic serve

\
\
參考資料 : [Jonny Huang 的學習筆記](https://jonny-huang.github.io/ionic/training/01_creating_first_project/)
