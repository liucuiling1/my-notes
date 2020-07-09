#### promise,callback,swith

(1):Promise
```js
new Promise((resolve, reject) => {
  wx.login({
    success: (res) => {
      resolve(res);
    },
    fail: (res) => {
      reject({
      code: 1,
      msg: '登录小程序失败'
      });
    }
  })
})
.then((res) => {
  console.log('小程序登录succsee')
  if (res && res.code) {
    return that.searchAuthorize(res.code); // 查询是否已授权
  }
})
.catch((err) => {
  console.log('err', err)
})
```
```js
  //或者引用
  onLoad: function(options) {

    new Promise((resolve, reject) => {

      this.getCarryFunc1(resolve, reject);

    }).then((res) => {
      console.log(res);

    }).catch((err) => {
      console.log('err', err);
    })

  },
  getCarryFunc1: function(resolve, reject) {
    let status = true;

    if (status) {

      let item = {
        name: 'cuiling',
        age: '25'
      }
      resolve(item);
    } else {
      resolve(false);
    }
  },
  
```
```js
 // 或者
  onLoad: function(options) {
    this.getCarryFunc1()
      .then((res) => {
        console.log(res);
        this.getCarryFunc2();

      }).catch((err) => {
        console.log('err', err);
      })
  },
  getCarryFunc1: function() {
    return new Promise((resolve, reject) => {

      let status = true;

      if (status) {
        let item = {
          name: 'cuiling',
          age: '25'
        }
        resolve(item);
      } else {

        resolve({
          status: false
        })
      }
    });
  },
  getCarryFunc2() {
    console.log('22');
  },
```
```js
onLoad: function(options) {
    new Promise((resolve, reject) => {
        this.getCarryFunc1(resolve);
      })
      .then((res) => {
        console.log(res);
        if (res.type == 1) {

          return this.getCarryFunc2()

          console.log(this.getCarryFunc2())
        }
      })
      .then((res) => {
        console.log(res);
        if (res.type == 2) {

          this.getCarryFunc3()
        }
      })
      .catch((err) => {
        console.log('err', err);
      })
  },

  getCarryFunc1(resolve) {
    console.log('11');
    resolve({
      type: 1

    })
  },
  getCarryFunc2() {
    console.log('22');
    return new Promise((resolve, reject) => {

      resolve({
        type: 2

      })
    })
  },
  getCarryFunc3() {
    console.log('33');
  },
```
(2)callback
```js
const changeEvent = (callback) => {
  wx.getSetting({
    success(res) {
    let _status = res.authSetting['scope.userLocation'];

    callback(_status);

    }
  })
}

module.exports = {
  changeEvent: changeEvent
}


```
其次页面引用
```js

import local from '../../utils/location.js’;

local.changeEvent((res) => {
  console.log(res)
})

```
(3) switch
```js
switch (res){
 case  true:
  ...
  break;
 case  false:
  ...
  break;
}
```
