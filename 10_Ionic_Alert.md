# Ionic Alert

在 APP 中，跳通知的功能在 ionic 中是 Alert 

[Alert](https://ionicframework.com/docs/api/alert) 在官網中提供了 4 種寫法

在我們 APP 中，我們只使用了 **ANGYLAR** 跟 **JAVASCRIPT** 


> **ANGYLAR**

ANGULAR 的寫法基本上可使用於 APP 任何需要跳通知的地方，除了在讀取 Firebase 的 function 中無法使用外

要使用 ionic 的 Alert 時，要先 **import** AlertController ，在把 AlertController 需告成全域變數

[asyns 跟 await](https://www.oxxostudio.tw/articles/201908/js-async-await.html) 的用意思，在這裡我們就不贅述，想要了解的話可以看一下連結的資料

\
buttons 可以有很多種，在 APP 中，我們常用到的就是**方法一**跟**方法二**

方法一 : 是很簡單的一個用法，只有讓你點掉它，你點什麼都跟他關係

方法二 : 多了一個讀取你按了什麼按鈕功能，我們可以依照用戶點選的內容來決定要做什麼資料的處理


```js
    import { AlertController } from '@ionic/angular';
    
    export class AlertExample {
    
        constructor(public alertController: AlertController) {}
        
        // 方法一
        async presentAlert() {
            const alert = await this.alertController.create({
              header: 'Alert',
              subHeader: 'Subtitle',
              message: 'This is an alert message.',
              buttons: ['OK']
            });

            await alert.present();
        }
        
        // 方法二
        async presentAlertConfirm() {
        const alert = await this.alertController.create({
            header: 'Confirm!',
            message: 'Message <strong>text</strong>!!!',
            buttons: [
              {
                  text: 'Cancel',
                  role: 'cancel',
                  cssClass: 'secondary',
                  handler: (blah) => {
                      console.log('Confirm Cancel: blah');
                  }
               }, {
                  text: 'Okay',
                  handler: () => {
                      console.log('Confirm Okay');
                  }
              }
            ]
        });

        await alert.present();
      }
        
    }
```
----------
> **JAVASCRIPT**

JAVASCRIPT 的寫法跟 ANGULAR 的些法差不多

差別就在於 function 放的地方不太一樣， JAVASCRIPT 是放在最外面， 其他的使用方式都跟 ANGULAR 一樣了
```js
    function presentAlert() {
      const alert = document.createElement('ion-alert');
      alert.header = 'Alert';
      alert.subHeader = 'Subtitle';
      alert.message = 'This is an alert message.';
      alert.buttons = ['OK'];

      document.body.appendChild(alert);
      return alert.present();
    }
```











