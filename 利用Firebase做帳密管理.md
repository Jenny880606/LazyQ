# 如何審核使用者登入的帳號密碼呢?

* 打開 /src/app/login/login.page.ts，設定 Firebase 需要的東西

      import { Component, OnInit } from '@angular/core';
      import { AngularFireAuth } from '@angular/fire/auth';
      import { auth } from 'firebase/app';
      import { UserService } from '../user.service';
      import { Router } from '@angular/router'

      @Component({
        selector: 'app-login',
        templateUrl: './login.page.html',
        styleUrls: ['./login.page.scss'],
      })
      
      export class LoginPage implements OnInit {
        username: string = ""
        password: string = ""
        constructor(
          public afAuth: AngularFireAuth, 
          public user: UserService, 
          public router: Router
        ) { }
      }
      
