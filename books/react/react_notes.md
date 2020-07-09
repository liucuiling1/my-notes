#### react_小记

(1)判断的简单方法，不用if
```js
let user_id = _data.user_id ? `user_id=${ _data.user_id }` : '';
let user_id1 = _data.user_id1 ? `&user_id1=${ _data.user_id1 }` :'';
url: `/ywym/grant?${ user_id }${ user_id1 }`,
```

(2)跳转
```js
location.href=`/ywym/download?application_ids=${ _dataActivate.application_id }`;

```

(3)更改状态之后再请求函数

```js
this.setState({
  page: value
}, () => {
  this.getList();
});
```

(4)下载文件
```js
let url = '/template/product_bind_template.xlsx';
window.open(url);
```

(5)判断数组里是否存在某个值
```js
  let _list=[1,2,3,4];
  let lily = _list.filter((p) => {
      return p == 1;
    });

  if (lily.length == 0) {
  }

```

(6)获取上个页面的传的参数
```js
getUrlData() {
  let urlArray = window.location.search.substring(1).split("&");
  let urlData = {};
  for (let i = 0; i < urlArray.length; i++) {
    let pair = urlArray[i].split('=');
    urlData[pair[0]] = decodeURI(pair[1]);
  }
  return urlData;
}
```


