#### webpack多个项目打包编译  npm-run-all

(1) 安装依赖包
> npm install npm-run-all --save-dev     
> or     
> yarn add npm-run-all --dev   

(2) package.json文件
```
  "scripts": {
    "build-login": "webpack --watch --config ./login/webpack.config.js",
    "build-admin": "webpack --watch --config ./admin/webpack.config.js",
    "start": "npm-run-all --parallel build-login build-admin"
  },
  "devDependencies": {
    "npm-run-all": "^4.1.5",
    "open": "^7.0.3"
  },
```

(3) 运行：npm run start;   
(4) npm-run-all 提供了多种运行多个命令的方式，常用的有以下几个：
  
>  --parallel: 并行运行多个命令，例如：npm-run-all --parallel lint build      
>  --serial: 多个命令按排列顺序执行，例如：npm-run-all --serial clean lint build:**    
>  --continue-on-error: 是否忽略错误，添加此参数 npm-run-all 会自动退出出错的命令，继续运行正常的     
>  --race: 添加此参数之后，只要有一个命令运行出错，那么 npm-run-all 就会结束掉全部的命令    


##### 第二种：webpack多个项目打包编译

(1) package.json文件
```
{
  "scripts": {
	  "build": "webpack --watch --config ./webpack.config.js",
    "build-login": "webpack --watch --config ./login/webpack.config.js",
    "build-admin": "webpack --watch --config ./admin/webpack.config.js",
  },
}
```

(2) webpack.config.js文件
```
entry: {
	"qr-code": "./qr-code/index.js",
	"wechat-registration-bind": "./wechat-registration-bind/index.js",
	"qr-merchant-manage": "./qr-merchant-manage/index.js",
},

output: {
	path: path.resolve(__dirname, "../../../public/js/"),
	filename: "[name].js",
},
```
（3）运行：npm run build





 