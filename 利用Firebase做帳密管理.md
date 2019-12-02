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
      
      
* 在 app 下面新增 user.service.ts
 
      	import { Injectable } from '@angular/core'
	  import { AngularFireAuth } from '@angular/fire/auth'
	  import { first } from 'rxjs/operators'
	  import { auth } from 'firebase/app'

	  interface user {
		username: string,
		uid: string
	  }

	  @Injectable()
	  export class UserService {
		  private user: user
		  constructor(private afAuth: AngularFireAuth) {}
		  
		  setUser(user: user) {
			  this.user = user
		  }
		  
		  getUsername(): string {
			  return this.user.username
		  }

		  async isAuthenticated() {
			  if(this.user) return true

			  const user = await this.afAuth.authState.pipe(first()).toPromise()

			  if(user) {
				  this.setUser({
					  username: user.email.split('@')[0],
					  uid: user.uid
				  })
				  return true
			  }
			  return false
		  }

		  getUID(): string {
			  return this.user.uid
		  }
	  }
 
     
加了這個ts檔，之後在其他頁面都可以呼叫裡面的 function

使用前提 : 

需要在最前面加入 import { UserService } from '../user.service'; 

在 constructor 裡面加入 public user: UserService

 
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
 
 
