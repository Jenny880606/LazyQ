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
      
* 把下面這個 function 寫進 login.page.ts 裡面

      async login() {
            const { username, password } = this
            try {
                  const res = await this.afAuth.auth.signInWithEmailAndPassword(username + '@lazyq.com',password);
                  if(res.user) {
		            this.user.setUser({
			            username,
				      uid: res.user.uid
		            })
			      this.router.navigate(['/home'])
		      }
            }catch(err) {
                  console.dir(err)
                  if(err.code == "auth/user-not-found"){
                        console.log("user not found")
                  }
            }
      }
      
 注意!!! 在這裡，帳號需要使用 username + '@lazyq.com' 喔~~
 
 因為 Firebase 裡面，帳號都是用信箱去判斷的，所以只要輸入是信箱格式就好了
 
 
