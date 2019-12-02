# Ionic + Firebase
>在cmd中輸入以下指令
* install the firebase @angular/fire

      npm install firebase @angular/fire --save
      
  
  
> 開啟 Firebase

網站連結: [Firebase](https://firebase.google.com/)

開啟後會看到這樣 ↓ ↓ ↓

<img src="教程圖片/start.png" width="ˇ250px" height="200px">



> 開啟 Firebase 專案


* 點擊《新增專案》

<img src="教程圖片/1.png" width="ˇ270px" height="200px">


* 填寫完專案名稱後，點擊《繼續》

<img src="教程圖片/2.png" width="ˇ270px" height="200px">


* 點擊《繼續》

<img src="教程圖片/3.png" width="ˇ270px" height="200px">


* 選取 Default Account for Firebase，點擊《建立專案》

<img src="教程圖片/4.png" width="ˇ270px" height="200px">


* 點擊《網頁》

<img src="教程圖片/5.png" width="ˇ270px" height="200px">


* 填寫應用程式暱稱，點擊《註冊應用程式》

<img src="教程圖片/6.png" width="ˇ270px" height="200px">


* 把紅色框起來的部分先複製一份

<img src="教程圖片/7.png" width="ˇ270px" height="200px">



> 連結 Ionic 和 Firebase


* 在 app 下面新增 firebase.ts
* 把剛剛複製的那段貼進 firebase.ts，並修改成這種格式

注意!!! 這邊要記得打自己的金鑰喔~~~

      const config = {
         apiKey: "AIzaSyB7kN3y7pTJKxbY58WcJnB9uLtpDFQuIEg",
         authDomain: "example-1d5b5.firebaseapp.com",
         databaseURL: "https://example-1d5b5.firebaseio.com",
         projectId: "example-1d5b5",
         storageBucket: "example-1d5b5.appspot.com",
         messagingSenderId: "322075177821",
         appId: "1:322075177821:web:d5bde438a04f3850556eb4",
         measurementId: "G-PRWVT396HF"
       };
      export default config
     
     
* 打開 /src/app/app.module.ts，設定 Firebase 需要的東西

      import firebaseConfig from './firebase'
      import { AngularFireModule } from '@angular/fire';
      import { AngularFireAuthModule } from '@angular/fire/auth'
      import { HttpModule } from '@angular/http'
      import { AngularFirestoreModule } from '@angular/fire/firestore';
      import { AuthService } from './auth.service';
      import { ShareModule } from './share.module';
      
      @NgModule({
      declarations: [AppComponent],
      entryComponents: [],
      imports: [
            BrowserModule,
            IonicModule.forRoot(),
            AppRoutingModule,
            AngularFireModule.initializeApp(firebaseConfig),
            AngularFireAuthModule,
            AngularFirestoreModule,
            FormsModule
      ],
      providers: [
            StatusBar,
            SplashScreen,
            { provide: RouteReuseStrategy, useClass: IonicRouteStrategy }
      ],
      bootstrap: [AppComponent]
      })
      
 網站影片: [Firebase + ionic 教學影片](https://www.youtube.com/watch?v=Q8zcieAWn3g&t=769s)
      
            
  


