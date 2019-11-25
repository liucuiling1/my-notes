#### frogmp项目codeview笔记（代码简洁/优化）

(1)三目运算符（可以代替if判断）
```
let user_id = _data.user_id ? `user_id=${ _data.user_id }` : '';
let user_id1 = _data.user_id1 ? `&user_id1=${ _data.user_id1 }` :'';
url: `/ywym/grant?${ user_id }${ user_id1 }`,
```

(2)跳转/下载文档直接使用location.href
```
location.href=`/ywym/download?application_ids=${ _dataActivate.application_id }`;
```

(3)this.setState回调函数
```
this.setState({
  page: value
}, () => {
  this.getList();
});
```

(4)下载文件
```
let url = '/template/product_bind_template.xlsx';
window.open(url);
```

(5)判断current是否存在
```
let lily = _list.filter((p) => {
  return p.current == value;
});
if (lily.length == 0) {}
```

(6)获取上个页面的传的参数
```
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




