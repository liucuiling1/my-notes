#### 笔记

引用页面：
```js
import local from '../../utils/location.js’;

local.changeEvent((res) => {

  console.log(res);  // 打印：返回参数

})
```

Js:

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
