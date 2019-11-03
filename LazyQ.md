# LazyQ+
學校宿舍的洗衣機、烘衣機的使用上總是非常沒有效率。經常有人隨意的插隊，使用後忘了自己正在排隊等待使用機台，或是忘了領取已經洗好烘乾的衣物。
使得機台的使用效率降低，造成住宿生許多不便。同時，宿舍洗烘衣機眾多，使用者無法快速得知各樓層機器的使用情況，即便是非尖峰時間也需要花費許多時間來往各層樓才能尋找到可以用的機器。因此，我們急需要一個具有系統和方便性的辦法來解決這些問題。\
\
因此，我們決定開發「LazyQ+」這個APP\
\
LazyQ+的功能有:
1. 使用者能用APP來得知各樓層機器的使用情況快速尋找到還沒被利用的機台
2. 透過線上系統進行有效的排隊
3. 即時提醒使用者機器可否使用或是衣物是否可被領取
4. 為了增加住宿生的便利性,我們亦規劃提供了「線上支付」和「線上預約機台」的功能

\
使用技術:
1. ionic
2. firebase
3. 樹梅派

## ionic 下載
參考資料: [ionic 下載說明](https://ionicframework.com/docs/installation/cli)\
以下說明為windows版本，在cmd中輸入以下指令
> install the ionic CLI and Cordova

    npm install -g ionic cordova
    
## 開始ionic專案
**( 小提醒 : 新專案的檔案位置和輸入cmd的資料夾是在同一個地方 )**
> start an app

    ionic start [<name>] [<template>]

*name* 是你這個專案的名稱\
*template* 是你個專案的版型，ionic有3種基本的版型 *blank*、*sidemenu*、*tabs*

在 LazyQ+ 中，我們是使用 *sidemenu* 這個版型作為基礎來修改

> 如何開始 coding ?

在這裡我們使用 [VS code](https://code.visualstudio.com/) 來做編寫程式\
在cmd中輸入

    code .

就會將整個檔案資料夾匯入 VS code 中


## 
